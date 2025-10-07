# pipeline-oliver

A Jenkins pipeline repository containing a Jenkinsfile for CI/CD automation.

## Overview

This repository contains a declarative Jenkinsfile that can be used with Jenkins to automate your build, test, and deployment processes.

## Usage

### Setting Up in Jenkins

1. **Create a New Pipeline Job:**
   - In Jenkins, click "New Item"
   - Enter a name for your pipeline
   - Select "Pipeline" and click "OK"

2. **Configure the Pipeline:**
   - In the pipeline configuration, scroll to the "Pipeline" section
   - Select "Pipeline script from SCM"
   - Choose "Git" as the SCM
   - Enter the repository URL: `https://github.com/OliverModinger7/pipeline-oliver.git`
   - Specify the branch (e.g., `*/main`)
   - Script Path: `Jenkinsfile` (default)
   - Click "Save"

3. **Run the Pipeline:**
   - Click "Build Now" to execute the pipeline
   - Monitor the progress in the build console output

### Pipeline Stages

The Jenkinsfile includes the following stages:

- **Checkout**: Checks out the source code from the repository
- **Build**: Compiles and builds the application
- **Test**: Runs automated tests
- **Deploy**: Deploys the application to the target environment

### Customization

To customize the pipeline for your specific project:

1. Edit the `Jenkinsfile` in this repository
2. Add your specific build commands (e.g., Maven, Gradle, npm)
3. Add your test commands
4. Add your deployment scripts
5. Commit and push your changes

### Example Customizations

**For a Maven project:**
```groovy
stage('Build') {
    steps {
        sh 'mvn clean package'
    }
}
```

**For a Node.js project:**
```groovy
stage('Build') {
    steps {
        sh 'npm install'
        sh 'npm run build'
    }
}
```

**For a Python project:**
```groovy
stage('Build') {
    steps {
        sh 'pip install -r requirements.txt'
    }
}
```

## Requirements

- Jenkins server with appropriate plugins installed
- Git plugin for Jenkins
- Pipeline plugin for Jenkins
- Appropriate build tools installed on Jenkins agents (Maven, npm, Python, etc.)

## Post Actions

The pipeline includes post-build actions:
- **Success**: Executes when the pipeline completes successfully
- **Failure**: Executes when the pipeline fails
- **Always**: Always executes regardless of build status

## Contributing

Feel free to modify the Jenkinsfile to suit your project's needs.