# Azure_NodeJS_RunNpmTest
This template enables us for using an Azure DevOps pipeline to build, deploy, and test JavaScript apps. This Template used for testing the property of a package.

## Parameters:

The pipeline requires the following parameters to be defined:

| Name | type | Default | Required/Optional | Comments |
| :-------------: | :-------------: | ------------- | :-------------: | :-------------: |
| filePath | String | $(Build.SourcesDirectory) | Required | define the filepath or working directory for package.json. Youc can also pass arguements  if required |
| npmTest | string | test | Optional | The value depends on command specified in package.json. Youc can also pass arguements  if required |


These parameters provide multiple use case options for the template, enable/disable flags for the utilization of different templates as per the requirements.


## Use Cases

You can directly call a particular template as per the requirement. for example: 

  ```yaml
  # azure-pipeline.yml
  resources:
  repositories:
    - repository: Template
      type: github
      name: your_username/Azure_NodeJS_RunNpmTest
      ref: <respective branch name>
      endpoint: 'githubServiceConnectioNname'

  steps:
  # passing the parameters
  - template: Azure_NodeJS_RunNpmTest.yml
    parameters:
        filePath: ${{ parameters.filePath }}
        npmTest: ${{ parameters.npmTest }}
        
Make sure to adjust the repository name, branch name, and parameter values according to your project's requirements.

  ```
