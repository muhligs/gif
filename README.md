# gif
Make gif files from R plots

gif() starts listening for plots to add to a gif file.
gif() takes the parameters file and delay and produces a temporary environment.
Delay sets the time each plot is visible in the gif.
Now use png.gif() in front of your plot command and close with dev.off() for each plot you wish to add to the gif.
When last plot of the gif is made, run gif.off().
This will produce the gif file in the current working directory.
If you want to see the file immidiately, run gif.off(TRUE).


Usage example


    setwd("~/temp")
    gif("smiley.gif",100)
    lapply(1:5,function(x){
	png.gif()
	plot(0:x,(0:x)^2,xlim=c(-11,11),ylim=c(0,200),axes=F,xlab="",ylab="")
	points(-1:-x,(1:x)^2)
	dev.off()
	})
    png.gif()
    plot(-5:5,(-5:5)^2,xlim=c(-11,11),ylim=c(0,200),axes=F,xlab="",ylab="")
    points(c(-3,3),c(50,50),cex=3,pch=20)
    dev.off()
    png.gif()
    plot(-5:5,(-5:5)^2,xlim=c(-11,11),ylim=c(0,200),axes=F,xlab="",ylab="")
    dev.off()
    png.gif()
    plot(-5:5,(-5:5)^2,xlim=c(-11,11),ylim=c(0,200),axes=F,xlab="",ylab="")
    points(c(-3,3),c(50,50),cex=3,pch=20)
    dev.off()
    gif.off(T)
