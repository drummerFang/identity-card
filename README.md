
China (region) citizen ID card tool
------------------------

>  China (Mainland) ID card package, the data from the national standard `GB / T 2260-2007` (People's Republic of China administrative divisions code standard).  

### Installing

```bash

    composer require anomalylab/component-identity-card
```


### Instructions


```php

    $idCard = Anomaly\Component\IdentityCard\IdentityCard::make('320106198310290811');
    //  Use locale, Current supported zh-cn,en
    // $idCard = Anomaly\Component\IdentityCard\IdentityCard::make('320106198310290811', 'zh-cn');

    try {
        $area = $idCard->getArea();
        $gender = $idCard->getGender();
        $birthday = $idCard->getBirthday();
        $age = $idCard->getAge();
        $constellation = $idCard->getConstellation();
    }
    catch (\Exception $e)
    {
        $e->getMessage();
    }
        


```


#### Results:
```json

{
    "area": "Jiang 南京市 鼓楼区",
    "gender": "male",
    "birthday": "1983-10-29",
    "age": 34,
    "constellation": "天蝎座"
}
```

### Api
- `getArea():string` 获取地区
- `getConstellation():string` 获取星座
- `getAge():int` 获取年龄
- `getBirthday(string $foramt = 'Y-m-d'):string` 获取生日
- `getGender():string` 获取性别
- `getCounty():string|null` 获取县城
- `getCity():string|null` 获取城市
- `getProvince():string|null` 获取省
