

MODULE = tpcorba/exo1
JAVA  = calculImpl.java Serveur.java Client.java
IDL   = server.idl

CLASS = $(JAVA:%.java=classes/$(MODULE)/%.class) 


all: idl src


src:	subdir $(CLASS)
idl:	subdir $(IDL:.idl=.jacorb)
	



############################################
## Do not change anything after this line
############################################

classes/$(MODULE)/%.class : %.java
	javac -d classes  $<

####

.SUFFIXES:
.SUFFIXES:      .idl .jacorb

.idl.jacorb:
	./idl -fall -td generated  $<
	javac -d classes generated/$(MODULE)/*.java
	touch $*.jacorb 

####

clean::
	rm -rf core *.jacorb *.ref 
	rm -rf classes generated

####

subdir:
	if [ ! -d classes ]; then \
	   mkdir classes;  \
	fi;
	if [ ! -d generated ]; then \
	   mkdir generated;  \
	fi;


