# docker-pgstudio container adapted for OpenShift

Example usage:

    # build and deploy the container from this repo
    oc new-app https://github.com/tourunen/docker-pgstudio
    
    # create a route for the service
    oc create route edge --service docker-pgstudio --insecure-policy=Redirect
    
    # deploy ephemeral postgresql from template
    # make note of the generated username and password
    oc new-app --template postgresql-ephemeral
    
    # get the generated hostname for the route
    oc get route docker-pgstudio

Then point your browser to the route host
  * connect to host 'postgresql'
  * use database 'sampledb'
  * use username and password from above
