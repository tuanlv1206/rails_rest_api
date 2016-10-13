# rails_rest_api

what is an API?
API stands for application programming interface. The term can be used to describe the features of a library, or how to interact with it.

However, these days, when people refer to an api the are most likely referring to an http api, which can be a way of sharing application data over the internet.

What is REST

REST stands for Representational State Transer. it describes a standard way of creating http apis.

REST is a lightweight alternative to mechanisms like RPC(Remote Procedure Calls) and Web Services.

Much like Web Services, a REST service is:

- Platform-independent(you dont care if the server is Unix, the client is a Mac, or anything else)
- Language-independent(C# can talk to Java, ect.)
- Standards-base(runs on top of http)
-Can easily be used in the presence of firewalls

It is a common convention in REST design to use nouns rather than verbs to denote simple resources


REST can easily handle more complex requests, including multiple parameters. In most cases, you'll just use http GET parameters in the URL.

For example:

http://www.acme.com/phonebook/UserDetails?firstName=John&lastName=Doe


If you need to pass long parameters, or binary ones, you'd normally use HTTP POST
requests, and include the parameters in the POST body.

As a rule, GET requests should be for read-only queries; they should not change the state
of the server and its data. For creation, updating, and deleting data, use POST
requests. (POST can also used for read-only queries, when complex parameters are
required.)

REST server response is often an XML file, other like CSV and JSON

REST architecture components

- Resources
- A web of resources
- There is no connection state
- Resources should be cachable whenever possible
- Proxy servers can be used as part of the architecture
