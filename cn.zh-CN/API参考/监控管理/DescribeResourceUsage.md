# DescribeResourceUsage {#doc_api_1106158 .reference}

调用DescribeResourceUsage接口查看实例的空间利用信息。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Rds&api=DescribeResourceUsage)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeResourceUsage|系统规定参数，取值：**DescribeResourceUsage**。

 |
|DBInstanceId|String|是|rm-uf6wjk5xxxxxxx|实例ID。

 |
|AccessKeyId|String|否|LTAIfCxxxxxxx|阿里云颁发给用户的访问服务所用的密钥ID。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DBInstanceId|String|rm-uf6wjk5xxxxxxx|实例名称。

 |
|Engine|String|MySQL|数据库类型。

 |
|DiskUsed|Long|2337275904|已用空间（DataSize+LogSize），单位：Byte。-1表示没有数据。

 |
|DataSize|Long|2337275904|数据文件占用空间，单位：Byte。-1表示没有数据。

 |
|LogSize|Long|2337275904|日志占用空间，单位：Byte。-1表示没有数据。

 |
|BackupSize|Long|53002759|备份占用空间，单位：Byte。-1表示没有数据。

 |
|ColdBackupSize|Long|2337275904|冷备的存储量，单位：Byte。-1表示没有数据。

 |
|SQLSize|Long|315052751|SQL的存储量，单位：Byte。-1表示没有数据。

 |
|BackupOssDataSize|Long|8821760|OSS中备份集的数据文件大小，单位：Byte。0表示没有数据。

 |
|BackupOssLogSize|Long|44180999|OSS中备份集的的日志文件大小，单位：Byte。0表示没有数据。

 |
|RequestId|String|A88722B7-DAEE-4822-BA8B-9B019FCB8D46|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://rds.aliyuncs.com/?Action=DescribeResourceUsage
&DBInstanceId=rm-uf6wjk5xxxxxxx
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeResourceUsageResponse>
  <BackupOssDataSize>8821760</BackupOssDataSize>
  <BackupOssLogSize>44180999</BackupOssLogSize>
  <RequestId>A88722B7-DAEE-4822-BA8B-9B019FCB8D46</RequestId>
  <DBInstanceId>rm-uf6wjk5xxxxxxx</DBInstanceId>
  <DataSize>2337275904</DataSize>
  <LogSize>-1</LogSize>
  <BackupSize>53002759</BackupSize>
  <SQLSize>315052751</SQLSize>
  <ColdBackupSize>-1</ColdBackupSize>
  <Engine>MySQL</Engine>
  <DiskUsed>2337275904</DiskUsed>
</DescribeResourceUsageResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"BackupOssLogSize":"44180999",
	"BackupOssDataSize":"8821760",
	"DBInstanceId":"rm-uf6wjk5xxxxxxx",
	"RequestId":"A88722B7-DAEE-4822-BA8B-9B019FCB8D46",
	"LogSize":-1,
	"DataSize":2337275904,
	"ColdBackupSize":-1,
	"SQLSize":315052751,
	"BackupSize":53002759,
	"Engine":"MySQL",
	"DiskUsed":2337275904
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Rds)

