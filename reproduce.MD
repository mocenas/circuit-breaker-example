# How to reproduce timeout "bug"

Name service is modified to insert artificial time delay to every request.
Circuit breaker should recognize this as a failure in service and open itself.

* Deploy this version of the booster: `mvn clean fabric8:deploy -Popenshift`
* Open web UI.
* Click "Invoke" Button.
* After some time (timeout) should the circuit breaker open and use fallback method, but it still waits for response.
