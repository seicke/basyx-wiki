# BaSyx AAS Submodel

"A Submodel defines a specific aspect of the asset represented by the Asset Administration Shell. A Submodel is used to structure the virtual representation and technical functionality of an Administration Shell into distinguishable parts. Each Submodel refers to a well-defined domain or subject matter. Submodels can become standardized and thus become submodels types. Submodels can have different life-cycles." (Details of the Asset Administration Shell, 2018, p. 46, [[1](https://www.plattform-i40.de/IP/Redaktion/DE/Downloads/Publikation/2018-verwaltungsschale-im-detail.pdf)])

Amongst the official attributes of Submodels, BaSyx defines aggregates called data elements, operations and events. These aggregates are used to structure official SubmodelElements (Property, ReferenceElement, Event, Operation, etc.) into groups of same functionality, i.e.

* DataElements as collection for value-based properties
* Operations as collection for callable methods
* Events as collection for events descriptions.
But the information model of a Submodel is only one side of the coin. BaSyx follows a distributed approach, i.e. Submodels may be deployed in distributed infrastructure. Asset Administration Shells only refer to their Submodels by terms of a reference comprising the Submodel's endpoints. They do not know about their Submodels' content but they know the way to it. On the other side, Submodels may reference their Asset Administration Shells as well via a parent attribute.

In order to access the Submodel's content, BaSyx defines so-called Submodel Service Providers. These Service Providers are used to make data elements, operations and events accessible by defining various access methods, e.g. GET- and SET- resp. MethodCalled-handler. Initially, on an abstract level, there is no technology binding necessary to build or use a service provider. Later of course, when starting the runtime, BaSyx provides highly generic technology bindings which can be used to grant access to the Submodel's content via chosen technology (HTTP/REST, OPC UA, BaSyx native).

In a nutshell, BaSyx Submodel Service Providers enable access to Submodels' content. A Submodel Service Provider needs to implement the generic Submodel Service Provider interface that is exemplary described on this page in HTTP/REST technology. The Submodel Service Provider enables access to data elements, operations and events. The BaSyx Submodel Service Provider may provide a façade hiding numerous (proprietary) data sources, e.g. SQL databases, XML configuration files, AutomationML, Hashmaps, Lambda, XQuery and many more. Furthermore, the BaSyx SDK enables creation of custom Submodel Service Providers. This is done by deriving from abstract BaSyx Service Provider interfaces.

The BaSyx Submodel Service Provider HTTP/REST API is explained [here](https://app.swaggerhub.com/apis/BaSyx/basyx_submodel_http_rest_api/v1).