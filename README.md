## To recreate the bug
Set up environment variable `GOOGLE_APPLICATION_CREDENTIALS` pointed to valid GCP credentials json file 

`./gradlew run`

This will create the exception 

>Message: getTransportChannel() called when needsExecutor() is true

## To work around the bug

Add 
>configurations.all {
>    resolutionStrategy {
>        force 'com.google.api:gax-grpc:2.0.0'
>    }
>}

To the build.gradle