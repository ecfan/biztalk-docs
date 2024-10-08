---
description: "Learn more about: Data provider properties for the Siebel connection string"
title: "Data provider properties for the Siebel connection string"
ms.custom: ""
ms.date: "06/08/2017"
ms.service: biztalk-server
ms.reviewer: ""
ms.suite: ""
ms.topic: "article"
---

# Data provider properties for the Siebel connection string

The [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) uses the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] to access the Siebel system. The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in turn uses the Siebel COM Data Control library to access the Siebel system. The Siebel COM Data Control comes bundled with the Siebel Web client.  

To establish connectivity to a Siebel system, ADO.NET clients must specify the Siebel connection properties that are encoded into a database connection string. This is required because the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] implements **DbConnection** to access the underlying [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding.  

The connection string connects to a Siebel system using the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] and looks like the following example:

```  
Username=YourUserName;Password=YourPassword;SiebelGateway=Siebel_Server:1234;SiebelObjectManager=obj_mgr;SiebelEnterpriseServer=ent_server;Language=enu;SiebelRepository=siebel_rep  
```  

[!INCLUDE [authentication-guidance](../../includes/authentication-guidance.md)]

The connections string contains the following properties:

| Property | Description |
|----------|-------------|
| Username | The user name on the Siebel system; this value is case-sensitive. <br><br>**Note:** The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] preserves the case of the value that you enter for the user name when it opens a connection on the Siebel system. |
| Password |The password for the user on the Siebel system; this value is case-sensitive. <br><br>**Note:** The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] preserves the case of the value that you enter for the password when it opens a connection on the Siebel system. |
| SiebelGateway | Consists of the Siebel server IP and port. For example, Siebel_Server:1234. |
| SiebelServer | The Siebel server. Required for all Siebel 7.5 server connections; otherwise, do not set this parameter. |
| SiebelObjectManager | The name of the Siebel object manager on the enterprise server. This parameter is required. |
| SiebelEnterpriseServer | The name of the Siebel Enterprise Server. This parameter is required. |
| Language | The language of the object manager. An example value is **enu**. This parameter is required. |
| SiebelRepository | The Siebel repository. Required if more than one repository exists on the server; otherwise, optional. <br><br>**Note:** If more than one repository exists on the server, you must specify a target repository in the SiebelRepository parameter. |
| Compression  | The compression algorithm to use between the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] and the Siebel system. Supported values are **none** or **zlib**. This parameter is optional. If it is not specified, the Siebel system supplies a default value (**zlib**). |
| Encryption | The type of encryption to use between the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] and the Siebel system. Supported values are **none**, **mscrypto**, or **rsa**. This parameter is optional. If it is not specified, the Siebel system supplies a default value (**none**). |
| Transport | The transport; only **tcpip** is supported. This parameter is optional. If it is not specified, the Siebel system supplies a default value (**tcpip**). |

## See also

[Use the .NET Framework Data Provider for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)
