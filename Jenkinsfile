node("master") {
    stage 'Checkout'
    git branch: 'master', url: 'https://github.com/kevensen/product-apim.git'

    // ** NOTE: This 'M3' maven tool must be configured in the global configuration.
    def mvnHome = tool 'M3'

    stage 'Build'
    sh "${mvnHome}/bin/mvn clean install -Dmaven.test.skip=true"

}
