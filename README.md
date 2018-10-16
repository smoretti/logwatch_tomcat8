# Description #
This is a set of custom filters and settings for monitoring different services with **logwatch** (https://sourceforge.net/projects/logwatch/). Copy this files in your _/etc/logwatch/_ or _/usr/share/logwatch/_ directory depending of your Linux OS.
# Services #
## Tomcat 8 ##
This service able to accumulate and summarize information about Errors in _catalina.out_ log file.
It has 2 modes:

*	**short** (logwatch detail level is LOW) - produse only information about total errors count and unique errors count
*	**full** (logwatch detail level is MED or HIGH) - additionally, produce error messages for every unique error

### Example ###
Short mode:
	
	
	--------------------- Tomcat 8 Begin ----------------------
	Unique errors: 2
	Total num of Errors: 18
	--------------------- Tomcat 8 End ------------------------

Full mode:
	
	--------------------- Tomcat 8 Begin ------------------------
	ERROR org.view.xml.XmlFactory 56 getErrorDisplay - throwing java.lang.UnsupportedOperationException: Not available for XML display
		at org.view.xml.XmlFactory.getErrorDisplay(XmlFactory.java:56)
	-------------------------------
	ERROR org.controller.FrontController 293 doRequest - catching org.controller.exception.InvalidFormatException: Incorrect parameter: search
		at org.controller.RequestParameters.throwIfInvalidFormatParamValue(RequestParameters.java:2831)
		at org.controller.RequestParameters.secureString(RequestParameters.java:2788)
	-------------------------------
	Unique errors: 2
	Total num of Errors: 18
	--------------------- Tomcat 8 End ------------------------
	
