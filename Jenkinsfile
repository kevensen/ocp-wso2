node("master") {
    // ** NOTE: This 'M3' maven tool must be configured in the global configuration.
    def mvnHome = tool 'M3'
    
    stage 'Checkout Carbon'
    sh "mkdir carbon-apimgt"
    dir path: carbon-apimgt
    git branch: '2.1', url: 'https://github.com/wso2/carbon-apimgt.git'

    stage 'Build Carbon'
    sh "mvn install -Dmaven.test.skip=true"

    stage 'Checkout'
    sh "cd .."
    sh "mkdir product-apim"
    dir path: product-apim
    git branch: '2.1.x', url: 'https://github.com/kevensen/product-apim.git'

    stage 'Build'
    sh "mvn install -Dmaven.test.skip=true"

}
