#!groovy

@Library("roboshop-shared-library") _
  
  // responsiblity to pass what type of application and comoponent into the pipeline deccission

  def configMap = [
    application = "nodejsVM",
    comoponent = "component"
  ]

  if (! env.BRANCH_NAME.equalsIgnoreCase('main')){
    pipelineDecission.decidepipeline(configMap)
  }
  else {
    echo "this is PROD this with CR process"
  }