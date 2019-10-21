Code for exercise of course R Programming / Código para el ejercicio de R Programming

CÓDIGO PARA CREAR LA FUNCIÓN COMPLETE DEL CURSO R PROGRAMMING

A continuación se comparte el código creado para la función COMPLETE. Si alguien encuentra alguna mejora es totalmente bienvenida.

In the next lines you can see the code written for create the function COMPLETE. If someone finds one improve, it's totally welcome

########### COMPLETE #################
##### AUTHOR: ESAÚ CONTRERAS
##### DATE : 2019-08-31
##### DESCRIPTION: FUNCTION FOR READ FILES AND COUNT
##### THE ROWS DIFFERENTS OF NA
##########################################

 #GET DIRECTORY
getwd()

 #SAVE THE PATH IN AN OBJECT
path<-"C:/Users/PC/Documents/specdata/"
path

 #SAVE THE FILES IN DIRECTORY IN AN OBJECT
files<-list.files("C:/Users/PC/Documents/specdata/")
files
	
 #FUNCTION DEFINITION
complete<-function( path,id=1:332) {
data2<-data.frame()
path<-"C:/Users/ETP/Documents/specdata/"
	for (i in id){
		data<-read.csv(paste0(path,files[i]),header=TRUE)
	data2<-rbind(data2,data)
}

data3<-subset(data2[!is.na(data2[2])&!is.na(data2[3]),])
data4<-as.data.frame(table(data3$ID))
colnames(data4)<-c("id","nobs")
data4
}

 #TEST FUNCTION

complete(path,278:274)
