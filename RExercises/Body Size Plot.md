#Body Size Evolution Plots#

### uses sizedata and timescale datasets ###

plot(1:10, xlab="Geologic Time (Ma)", ylab="Biovolume (log10mm^3)", xlim=c(550,0), ylim=c(-2,12))

chordata <- sizedata[which(sizedata[,"phylum"]=="Chordata"),]  
arthropoda <- sizedata[which(sizedata[,"phylum"]=="Arthropoda"),]  
brachiopoda <- sizedata[which(sizedata[,"phylum"]=="Brachiopoda"),]  
echinodermata <- sizedata[which(sizedata[,"phylum"]=="Echinodermata"),]  
mollusca <- sizedata[which(sizedata[,"phylum"]=="Mollusca"),]  

segments(chordata$fad_age,chordata$log10_volume,chordata$lad_age,chordata$log10_volume, col="purple")  
segments(mollusca$fad_age,mollusca$log10_volume,mollusca$lad_age,mollusca$log10_volume, col="blue")  
segments(echinodermata$fad_age, echinodermata$log10_volume, echinodermata$lad_age, echinodermata$log10_volume, col="green")  
segments(brachiopoda$fad_age, brachiopoda$log10_volume, brachiopoda$lad_age, brachiopoda$log10_volume, col="yellow")  
segments(arthropoda$fad_age, arthropoda$log10_volume, arthropoda$lad_age, arthropoda$log10_volume,col="red")  

meanVector <- vector(mode='numeric', length=nrow(timescale))  
my05 <- vector(mode='numeric', length=nrow(timescale))  
my95 <- vector(mode='numeric', length=nrow(timescale))  

for(i in 1:nrow(timescale)) {   
	meanVector[i] <- mean(sizedata$log10_volume[sizedata$fad_age > timescale$age_top[i] & sizedata$lad_age < timescale$age_bottom[i]])   
	my05[i] <- quantile(sizedata$log10_volume[sizedata$fad_age > timescale$age_top[i] & sizedata$lad_age < timescale$age_bottom[i]],0.05)  
	my95[i] <- quantile(sizedata$log10_volume[sizedata$fad_age > timescale$age_top[i] & sizedata$lad_age < timescale$age_bottom[i]],0.95)  	  
	}  
	
lines(x=timescale$age_mid,y=meanVector, col="black", lwd=2.5)  
lines(x=timescale$age_mid,y=my05, col="black")  
lines(x=timescale$age_mid,y=my95, col="black")  
