# composer aliyun Open API SDK for php developers

## Requirements

- PHP 5.4+

## Install

``` bash
$ composer require heroin/aliyun-openapi-php-sdk
```

## Example

```php
use Heroin\Aliyun\Core\Profile\DefaultProfile;
use Heroin\Aliyun\Core\Regions\Config;
use Heroin\Aliyun\Core\DefaultAcsClient;

$config = new Config();
$c->setEndPoint();
$iClientProfile = DefaultProfile::getProfile("cn-shanghai", 'accessKeyId', 'accessKeySecret');
DefaultProfile::addEndpoint("cn-shanghai", "cn-shanghai", "Green", "green.cn-shanghai.aliyuncs.com");

$client = new DefaultAcsClient($iClientProfile);

$request = new GreenTextService();
$request->setMethod("POST");
$request->setAcceptFormat("JSON");

$task1 = array('dataId' =>  uniqid(),
'content' => 'hello word'
);
$request->setContent(json_encode(array("tasks" => array($task1),
"scenes" => array("antispam"))));
$response = $client->getAcsResponse($request);
print_r($response);
```
## Authors && Contributors

- [xia wenqiang](https://github.com/406413214)

## License

licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0.html)