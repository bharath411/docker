node {
   // Mark the code checkout 'stage'....
   stage 'Checkout'
   
   checkout scm

   // Get the maven tool.
   // ** NOTE: This 'M3' maven tool must be configured
   // **       in the global configuration.           
   def mvnHome = tool 'maven'

   // Mark the code build 'stage'....
   stage 'Build'
   // Run the maven build
   sh "${mvnHome}/bin/mvn  clean package"
   sh "${mvnHome}/bin/mvn  --settings ./.mvn/settings.xml dockerfile:build"
   sh "${mvnHome}/bin/mvn  --settings ./.mvn/settings.xml dockerfile:push"
   
}