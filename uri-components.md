## URI Components
###Hostname

Make no assumption about the hostname. 
Assume that each API will have a different hostname. In particular do not assume a specific IP address. Services can be dynamically deployed or moved. 
DNS was invented to deal with that.

###Service namespace

In any URI, the first noun (which may be singular or plural, depending on the situation) should be considered a “Service namespace”. Service namespaces should reflect the customer's perspective on the (business) service boundary.

Do not use acronyms. Use small caps and underscore ‘_’ for ‘space’ (governs all of the url and messages). 

#####URI Template

	/{namespace}/

#####Example

	/user_management/

###Version

The URI should include /vN with the major version (N) as a prefix. No major.minor syntax.
URL-based versioning is utilized for it's simplicity of use for API consumers, versus the more complex header-based approach.  

> Version is a single number and only to be incremented on ‘backward’ compatibility breaking.  
> Adding fields or deprecating fileds are NOT breaking changes. API Clients need to be able to ignore additional 
> elements. API Providers need to be able to use meaningful defaults for additional fields not provided by existing > clients.  
> Prevent from increasing the version as long as possible.

Currently their is no certificatiion or validation process for clients to proove for proper behavior. Each client is responsible to test its implemenation.

#####URI Template

	/{namespace}/v{version}/

#####Example

	/user_management/v1/

### Resource References

The URI references for resources should consistenly use the same path components to refer to resources. Sub-namespace or sub-folders should be avoided, to maintain path consistency. This allows consumer developers to have a predictable experience in case they are building URIs in code.

#####URI Template

	/{namespace}/{version}/{resource}/{resource-id}/{sub-resource}/{sub-resource-id}
 


 
