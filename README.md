<#if api.picture??>
<img src="${api.picture}" style="float: right;max-width: 60px;"/>
</#if>

# Welcome to the API page of ${api.name}(${api.version})!

The API is <span style="text-transform: lowercase;color: <#if api.state=='STARTED'>green<#else>red</#if>">${api.state}</span>.

This API has been created on ${api.createdAt?datetime} and updated on ${api.updatedAt?datetime}.

<#if api.deployedAt??>
This API has been deployed on ${api.deployedAt?datetime}.
<#else>
This API has not yet been deployed.
</#if>

<#if api.visibility=='PUBLIC'>
This API is publicly exposed.
<#else>
This API is not publicly exposed.
</#if>

<#if api.tags?has_content>
Sharding tags: ${api.tags?join(", ")}
</#if>

## Description

${api.description}

## Changelog

v1.0 - Initial release

## How to access

The API can be accessed through https://api.company.com${api.proxy.contextPath}:

curl https://api.company.com${api.proxy.contextPath}

## Rating

You can rate and put a comment for this API <a href='/#!/apis/${api.id}/ratings'>here</a>.

## Contact

The support contact is <a href="mailto:${api.metadata['email-support']}">${api.metadata['email-support']}</a>.

The API owner is <#if api.primaryOwner.email??><a href="mailto:${api.primaryOwner.email}">${api.primaryOwner.displayName}</a><#else>${api.primaryOwner.displayName}</#if>.
