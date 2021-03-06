# ModifyDBInstanceSpec {#doc_api_1063465 .reference}

You can call this operation to modify the type or storage space of an instance. The instance can be a regular or read-only instance, and cannot be a disaster recovery or temporary instance.

This operation must meet the following requirements:

-   The instance is in the running state.
-   The instance is not performing a backup task.
-   Either the instance type \(DBInstanceClass\) or storage space \(DBInstanceStorage\) parameter must be specified in the request.
-   When you downgrade the disk space configuration, the input disk space is no less than 1.1 times the actually used space.
-   Only regular and read-only instances allow configuration changes. Configurations cannot be changed for disaster recovery or temporary instances.

## Debugging {#apiExplorer .section}

You can use [API Explorer](https://api.aliyun.com/#product=Rds&api=ModifyDBInstanceSpec) to perform debugging. API Explorer allows you to perform various operations to simplify API usage. For example, you can retrieve APIs, call APIs, and dynamically generate SDK example code.

## Request parameters {#parameters .section}

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ModifyDBInstanceSpec| The operation that you want to perform. Set the value to **ModifyDBInstanceSpec**.

 |
|DBInstanceId|String|Yes|rm-uf6wjk5xxxxxxx| The ID of the instance.

 |
|PayType|String|Yes|Postpaid| The current billing method of the instnace. Valid values:

 -   **Postpaid**
-   **Prepaid**

 |
|ClientToken|String|No|ETnLKlblzczshOTUbOCzxxxxxxx| The client token that is used to ensure the idempotency of requests. The parameter value is generated by the client and is unique among different requests, which is a string of up to 64 ASCII characters.

 |
|DBInstanceClass|String|No|rds.mys2.small| The type of the instance. For more information, see [Instance types](~~26312~~).

 **Note:** Either the instance type \(DBInstanceClass\) or storage space \(DBInstanceStorage\) parameter must be specified in the request.

 |
|DBInstanceStorage|Integer|No|20| User-defined storage space. The value must be an integer multiple of 5. Valid values:

 -   MySQL: **5 to 2000**.
-   SQL Server: **10 to 3000**.
-   PostgreSQL: **5 to 2000**.
-   PPAS: **250 to 500**.
-   MariaDB: **20 to 1000**.

 Different billing methods and instances of different versions have different value ranges. For more information, see the read-only instance creation page in the console.

 **Note:** Either the instance type \(DBInstanceClass\) or storage space \(DBInstanceStorage\) parameter must be specified in the request.

 |
|EffectiveTime|String|No|2017-11-06T17:49:12Z| Effective time. Valid values:

 -   **Immediate**: The changes take effect immediately.
-   **MaintainTime**: The changes take effect during the maintenance period. For more information about the maintenance period, see [ModifyDBInstanceMaintainTime](~~26249~~).

 Default value: **Immediate**.

 |
|EngineVersion|String|No|5.6| The version of the database. Valid values:

 -   MySQL: **5.5/5.6/5.7**
-   SQLServer: **2008r2/2012/2012\_ent\_ha/2012\_std\_ha/2012\_web/2016\_ent\_ha/2016\_std\_ha/2016\_web/2017\_ent**
-   PostgreSQL: **9.4/10.0**
-   PPAS: **9.3/10.0**
-   MariaDB: **10.3**

 |
|AccessKeyId|String|No|LTAIfCxxxxxxxxxx| The AccessKey ID that Alibaba Cloud issues to a user for service access.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|3C5CFDEE-F774-4DED-89A2-1D76EC63C575| The ID of the request.

 |

## Examples {#demo .section}

Sample requests

``` {#request_demo}

http(s)://rds.aliyuncs.com/? Action=ModifyDBInstanceSpec
&DBInstanceId=rm-uf6wjk5xxxxxxx 
&PayType=Postpaid 
&DBInstanceClass=rds.mys2.small
&<Common request parameters>

```

Successful response examples

`XML` format

``` {#xml_return_success_demo}
<ModifyDBInstanceSpecResponse> 
  <RequestId>3C5CFDEE-F774-4DED-89A2-1D76EC63C575</RequestId>
</ModifyDBInstanceSpecResponse> 

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":" 3C5CFDEE-F774-4DED-89A2-1D76EC63C575 "
}
```

## Error codes {#section_p9q_6oi_mrb .section}

[View error codes](https://error-center.aliyun.com/status/product/Rds)

