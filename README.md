# Cache Java and Maven Dependencies Action

This GitHub Action allows caching both Java and Maven Dependencies based on the pom.xml file.

**Inputs**

* **java-version**:

  * Description: Java version to use.
  * Default: '11'
  * Required: true

* **working-dir**:

  * Description: The working directory of the application.
  * Default: '.'
  * Required: false
  
**Usage**

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout code
      uses: actions/checkout@v2

    - name: Cache Java and Maven Dependencies
      uses: PadmanabhanSaravanan/cache-deps@v1
            
      with:
        java-version: '11'
        working-dir: '.'

    - name: Build and Test
      run: mvn clean install
      working-directory: ${{ inputs.working-dir }}
```
