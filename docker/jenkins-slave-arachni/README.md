# jenkins-slave-arachni
Provides a docker image of the arachni security tool with an additional reporter for generating xunit reports. These can be parsed into test results for failing builds using JUnit parser in Bamboo and Jenkins.

## Build
`docker build -t jenkins-slave-arachni .`

## Run
For local running and experimentation run `docker run -i -t --rm jenkins-slave-arachni /bin/bash` and have a play once inside the container. `/arachni` is where the product is and  `/arachni/bin/arachni` for the binary

## Jenkins running
Creates a HTML web report and xml report once website has been scanned. Add a new Kubernetes Container template called `jenkins-slave-arachni` and specify this as the node when running builds

```bash
/arachni/bin/arachni ${URL_TO_TEST} --report-save-path=arachni-report.afr
/arachni/bin/arachni_reporter arachni-report.afr  --reporter=xunit:outfile=report.xml  --reporter=html:outfile=web-report.zip
unzip web-report.zip -d arachni-web-report
```
