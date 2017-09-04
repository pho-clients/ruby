# PhoClient::DefaultApi

All URIs are relative to *https://virtserver.swaggerhub.com/phonetworks/server-rest/1.1.0*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_attribute**](DefaultApi.md#add_attribute) | **POST** /{uuid}/attribute/{key} | updates (or creates) an attribute
[**del_attribute**](DefaultApi.md#del_attribute) | **DELETE** /{uuid}/attribute/{key} | deletes an attribute
[**del_entity**](DefaultApi.md#del_entity) | **DELETE** /{uuid} | deletes an entity
[**get_all_edges**](DefaultApi.md#get_all_edges) | **GET** /{uuid}/edges/all | retrieves the edges of a node
[**get_attribute**](DefaultApi.md#get_attribute) | **GET** /{uuid}/attribute/{key} | retrieves the value of an entity attribute
[**get_attributes**](DefaultApi.md#get_attributes) | **GET** /{uuid}/attributes | retrieves the existing attribute keys of an entity (edge or node)
[**get_edge**](DefaultApi.md#get_edge) | **GET** /edge/{uuid} | retrieves an edge
[**get_edge_getters**](DefaultApi.md#get_edge_getters) | **GET** /{uuid}/edges/getters | retrieves the edge getter methods of a node
[**get_edge_setters**](DefaultApi.md#get_edge_setters) | **GET** /{uuid}/edges/setters | retrieves the edge setter methods of a node
[**get_founder**](DefaultApi.md#get_founder) | **GET** /founder | retrieves the Graph Founder
[**get_graph**](DefaultApi.md#get_graph) | **GET** /graph | retrieves the main Graph
[**get_incoming_edges**](DefaultApi.md#get_incoming_edges) | **GET** /{uuid}/edges/in | retrieves the incoming edges of a node
[**get_node**](DefaultApi.md#get_node) | **GET** /{uuid} | retrieves a node
[**get_node_edge**](DefaultApi.md#get_node_edge) | **GET** /{uuid}/{edge} | edge getter
[**get_outgoing_edges**](DefaultApi.md#get_outgoing_edges) | **GET** /{uuid}/edges/out | retrieves the outgoing edges of a node
[**get_space**](DefaultApi.md#get_space) | **GET** /space | retrieves the Space
[**get_type**](DefaultApi.md#get_type) | **GET** /{uuid}/type | fetches entity type
[**make_actor**](DefaultApi.md#make_actor) | **POST** /actor | creates an Actor object
[**make_edge**](DefaultApi.md#make_edge) | **POST** /{uuid}/{edge} | creates an edge
[**set_attribute**](DefaultApi.md#set_attribute) | **PUT** /{uuid}/attribute/{key} | updates (or creates) an attribute


# **add_attribute**
> InlineResponse2004 add_attribute(opts)

updates (or creates) an attribute

Works with all entities, including nodes and edges. Given its key, updates an  attribute value, or creates it, if it doesn't yet exist. 

### Example
```ruby
# load the gem
require 'pho_client'

api_instance = PhoClient::DefaultApi.new

opts = { 
  value: "value_example" # String | The value to update the key with.
}

begin
  #updates (or creates) an attribute
  result = api_instance.add_attribute(opts)
  p result
rescue PhoClient::ApiError => e
  puts "Exception when calling DefaultApi->add_attribute: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **value** | **String**| The value to update the key with. | [optional] 

### Return type

[**InlineResponse2004**](InlineResponse2004.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **del_attribute**
> InlineResponse2004 del_attribute

deletes an attribute

Works with all entities, including nodes and edges. Given its key, deletes an  attribute. 

### Example
```ruby
# load the gem
require 'pho_client'

api_instance = PhoClient::DefaultApi.new

begin
  #deletes an attribute
  result = api_instance.del_attribute
  p result
rescue PhoClient::ApiError => e
  puts "Exception when calling DefaultApi->del_attribute: #{e}"
end
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**InlineResponse2004**](InlineResponse2004.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **del_entity**
> del_entity

deletes an entity

Works with all entities, including nodes and edges.  

### Example
```ruby
# load the gem
require 'pho_client'

api_instance = PhoClient::DefaultApi.new

begin
  #deletes an entity
  api_instance.del_entity
rescue PhoClient::ApiError => e
  puts "Exception when calling DefaultApi->del_entity: #{e}"
end
```

### Parameters
This endpoint does not need any parameter.

### Return type

nil (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **get_all_edges**
> InlineResponse2003 get_all_edges(uuid)

retrieves the edges of a node

By passing in a node ID, you can fetch all the edges of the node in question; including incoming and outgoing. 

### Example
```ruby
# load the gem
require 'pho_client'

api_instance = PhoClient::DefaultApi.new

uuid = "uuid_example" # String | The node ID


begin
  #retrieves the edges of a node
  result = api_instance.get_all_edges(uuid)
  p result
rescue PhoClient::ApiError => e
  puts "Exception when calling DefaultApi->get_all_edges: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **uuid** | **String**| The node ID | 

### Return type

[**InlineResponse2003**](InlineResponse2003.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **get_attribute**
> String get_attribute(uuid, key)

retrieves the value of an entity attribute

Attribute key must be case-sensitive. 

### Example
```ruby
# load the gem
require 'pho_client'

api_instance = PhoClient::DefaultApi.new

uuid = "uuid_example" # String | The node ID

key = "key_example" # String | The attribute key


begin
  #retrieves the value of an entity attribute
  result = api_instance.get_attribute(uuid, key)
  p result
rescue PhoClient::ApiError => e
  puts "Exception when calling DefaultApi->get_attribute: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **uuid** | **String**| The node ID | 
 **key** | **String**| The attribute key | 

### Return type

**String**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **get_attributes**
> Array&lt;String&gt; get_attributes(uuid)

retrieves the existing attribute keys of an entity (edge or node)

Attribute keys are case-sensitive, and they will be listed in an array. 

### Example
```ruby
# load the gem
require 'pho_client'

api_instance = PhoClient::DefaultApi.new

uuid = "uuid_example" # String | The node ID


begin
  #retrieves the existing attribute keys of an entity (edge or node)
  result = api_instance.get_attributes(uuid)
  p result
rescue PhoClient::ApiError => e
  puts "Exception when calling DefaultApi->get_attributes: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **uuid** | **String**| The node ID | 

### Return type

**Array&lt;String&gt;**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **get_edge**
> Edge get_edge(uuid)

retrieves an edge

By passing in an ID, you can search for available edges in the system.  

### Example
```ruby
# load the gem
require 'pho_client'

api_instance = PhoClient::DefaultApi.new

uuid = "uuid_example" # String | The edge ID


begin
  #retrieves an edge
  result = api_instance.get_edge(uuid)
  p result
rescue PhoClient::ApiError => e
  puts "Exception when calling DefaultApi->get_edge: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **uuid** | **String**| The edge ID | 

### Return type

[**Edge**](Edge.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **get_edge_getters**
> Array&lt;String&gt; get_edge_getters(uuid)

retrieves the edge getter methods of a node

By passing in a node UUID that exists in the database, you can fetch  the edge getter methods of the node in question. 

### Example
```ruby
# load the gem
require 'pho_client'

api_instance = PhoClient::DefaultApi.new

uuid = "uuid_example" # String | The node ID


begin
  #retrieves the edge getter methods of a node
  result = api_instance.get_edge_getters(uuid)
  p result
rescue PhoClient::ApiError => e
  puts "Exception when calling DefaultApi->get_edge_getters: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **uuid** | **String**| The node ID | 

### Return type

**Array&lt;String&gt;**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **get_edge_setters**
> Array&lt;String&gt; get_edge_setters(uuid)

retrieves the edge setter methods of a node

By passing in a node UUID that exists in the database, you can fetch  the edge setter methods of the node in question. These setters may or  may not be formative. If they are formative, a new node is created in result. 

### Example
```ruby
# load the gem
require 'pho_client'

api_instance = PhoClient::DefaultApi.new

uuid = "uuid_example" # String | The node ID


begin
  #retrieves the edge setter methods of a node
  result = api_instance.get_edge_setters(uuid)
  p result
rescue PhoClient::ApiError => e
  puts "Exception when calling DefaultApi->get_edge_setters: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **uuid** | **String**| The node ID | 

### Return type

**Array&lt;String&gt;**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **get_founder**
> InlineResponse200 get_founder

retrieves the Graph Founder

The Founder must be a \\Pho\\Framework\\Actor object.  This method returns the object type as well as object ID. 

### Example
```ruby
# load the gem
require 'pho_client'

api_instance = PhoClient::DefaultApi.new

begin
  #retrieves the Graph Founder
  result = api_instance.get_founder
  p result
rescue PhoClient::ApiError => e
  puts "Exception when calling DefaultApi->get_founder: #{e}"
end
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**InlineResponse200**](InlineResponse200.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **get_graph**
> InlineResponse2001 get_graph

retrieves the main Graph

The Graph must be a \\Pho\\Lib\\Graph\\SubGraph and \\Pho\\Framework\\Graph object.  This method returns the object type as well as object ID. The Graph contains all nodes and edges in the system.  Though it is contained by Space, its one and only container. 

### Example
```ruby
# load the gem
require 'pho_client'

api_instance = PhoClient::DefaultApi.new

begin
  #retrieves the main Graph
  result = api_instance.get_graph
  p result
rescue PhoClient::ApiError => e
  puts "Exception when calling DefaultApi->get_graph: #{e}"
end
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**InlineResponse2001**](InlineResponse2001.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **get_incoming_edges**
> Array&lt;NodeEdge&gt; get_incoming_edges(uuid)

retrieves the incoming edges of a node

By passing in a node ID, you can fetch  the incoming edges of the node in question. 

### Example
```ruby
# load the gem
require 'pho_client'

api_instance = PhoClient::DefaultApi.new

uuid = "uuid_example" # String | the node ID


begin
  #retrieves the incoming edges of a node
  result = api_instance.get_incoming_edges(uuid)
  p result
rescue PhoClient::ApiError => e
  puts "Exception when calling DefaultApi->get_incoming_edges: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **uuid** | **String**| the node ID | 

### Return type

[**Array&lt;NodeEdge&gt;**](NodeEdge.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **get_node**
> Node get_node(uuid)

retrieves a node

By passing in an ID, you can search for available nodes in the system. Please note, this function will not return edges. This method  is  reserved for nodes only.  

### Example
```ruby
# load the gem
require 'pho_client'

api_instance = PhoClient::DefaultApi.new

uuid = "uuid_example" # String | The node ID


begin
  #retrieves a node
  result = api_instance.get_node(uuid)
  p result
rescue PhoClient::ApiError => e
  puts "Exception when calling DefaultApi->get_node: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **uuid** | **String**| The node ID | 

### Return type

[**Node**](Node.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **get_node_edge**
> Array&lt;String&gt; get_node_edge(uuid, edge)

edge getter

Fetches edge results, whether as edge IDs or node IDs, depending on edge's characteristics.  

### Example
```ruby
# load the gem
require 'pho_client'

api_instance = PhoClient::DefaultApi.new

uuid = "uuid_example" # String | The node ID

edge = "edge_example" # String | The edge getter label


begin
  #edge getter
  result = api_instance.get_node_edge(uuid, edge)
  p result
rescue PhoClient::ApiError => e
  puts "Exception when calling DefaultApi->get_node_edge: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **uuid** | **String**| The node ID | 
 **edge** | **String**| The edge getter label | 

### Return type

**Array&lt;String&gt;**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **get_outgoing_edges**
> Array&lt;NodeEdge&gt; get_outgoing_edges(uuid)

retrieves the outgoing edges of a node

By passing in a node ID, you can fetch  the outgoing edges of the node in question. 

### Example
```ruby
# load the gem
require 'pho_client'

api_instance = PhoClient::DefaultApi.new

uuid = "uuid_example" # String | the node ID


begin
  #retrieves the outgoing edges of a node
  result = api_instance.get_outgoing_edges(uuid)
  p result
rescue PhoClient::ApiError => e
  puts "Exception when calling DefaultApi->get_outgoing_edges: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **uuid** | **String**| the node ID | 

### Return type

[**Array&lt;NodeEdge&gt;**](NodeEdge.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **get_space**
> InlineResponse2002 get_space

retrieves the Space

The Space must be a \\Pho\\Lib\\Graph\\Graph object.  This method returns the object type as well as object uuid. Space always comes with the nil ID;  00000000000000000000000000000000, and under normal circumstances its class is always Pho\\Kernel\\Standards\\Space 

### Example
```ruby
# load the gem
require 'pho_client'

api_instance = PhoClient::DefaultApi.new

begin
  #retrieves the Space
  result = api_instance.get_space
  p result
rescue PhoClient::ApiError => e
  puts "Exception when calling DefaultApi->get_space: #{e}"
end
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**InlineResponse2002**](InlineResponse2002.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **get_type**
> String get_type(uuid)

fetches entity type

Possible values are; \"Space\", \"Node\", \"Graph Node\", \"Graph\", \"Actor Node\" \"Object Node\", \"Edge\", \"Read Edge\", \"Write Edge\", \"Subscribe Edge\", \"Mention Edge\", \"Unidentified\". 

### Example
```ruby
# load the gem
require 'pho_client'

api_instance = PhoClient::DefaultApi.new

uuid = "uuid_example" # String | the node


begin
  #fetches entity type
  result = api_instance.get_type(uuid)
  p result
rescue PhoClient::ApiError => e
  puts "Exception when calling DefaultApi->get_type: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **uuid** | **String**| the node | 

### Return type

**String**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **make_actor**
> String make_actor(opts)

creates an Actor object

Fetches whatever set as \"default_object\"=>\"actor\" while determining what Actor object to construct. If it doesn't exist, uses \"default_object\"=>\"founder\" class. Otherwise fails. 

### Example
```ruby
# load the gem
require 'pho_client'

api_instance = PhoClient::DefaultApi.new

opts = { 
  param1: "param1_example" # String | Actor constructor argument. More parameters may be passed via param2, param3 ... param50. 
}

begin
  #creates an Actor object
  result = api_instance.make_actor(opts)
  p result
rescue PhoClient::ApiError => e
  puts "Exception when calling DefaultApi->make_actor: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **param1** | **String**| Actor constructor argument. More parameters may be passed via param2, param3 ... param50.  | [optional] 

### Return type

**String**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json



# **make_edge**
> String make_edge(opts)

creates an edge

Used to set new edges. If the edge is formative, then a node is also formed. 

### Example
```ruby
# load the gem
require 'pho_client'

api_instance = PhoClient::DefaultApi.new

opts = { 
  param1: "param1_example" # String | The value to update the key with. There can be 50 of those. For example;  param1=\"value1\", param2 =\"another value\" depending on the edge's default constructor variable count. 
}

begin
  #creates an edge
  result = api_instance.make_edge(opts)
  p result
rescue PhoClient::ApiError => e
  puts "Exception when calling DefaultApi->make_edge: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **param1** | **String**| The value to update the key with. There can be 50 of those. For example;  param1&#x3D;\&quot;value1\&quot;, param2 &#x3D;\&quot;another value\&quot; depending on the edge&#39;s default constructor variable count.  | [optional] 

### Return type

**String**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



# **set_attribute**
> InlineResponse2004 set_attribute(opts)

updates (or creates) an attribute

Works with all entities, including nodes and edges. Given its key, updates an  attribute value, or creates it, if it doesn't yet exist. 

### Example
```ruby
# load the gem
require 'pho_client'

api_instance = PhoClient::DefaultApi.new

opts = { 
  value: "value_example" # String | The value to update the key with.
}

begin
  #updates (or creates) an attribute
  result = api_instance.set_attribute(opts)
  p result
rescue PhoClient::ApiError => e
  puts "Exception when calling DefaultApi->set_attribute: #{e}"
end
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **value** | **String**| The value to update the key with. | [optional] 

### Return type

[**InlineResponse2004**](InlineResponse2004.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json



