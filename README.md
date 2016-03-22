# Lumen & Dingo API Demo

## 基于Lumen5.2的配置

```
# Step 0: composer.json
"dingo/api": "1.0.*@dev"

# Step 1: vim bootstrap/app.php and add:
$app->register(Dingo\Api\Provider\LumenServiceProvider::class);

# 问题：Unable to boot ApiServiceProvider, configure an API domain or prefix. 
解决：必须配置完第二步才行

# Step 2: vim .env and add:
API_STANDARDS_TREE=vnd
API_SUBTYPE=dingoapi-demo
API_DOMAIN=lumen.test.com
API_PREFIX=api
API_VERSION=v1
API_NAME="Lumen & Dingo API Demo"
API_CONDITIONAL_REQUEST=false
API_STRICT=false
API_DEFAULT_FORMAT=json
API_DEBUG=true


# Step 3: 启动配置, vim bootstrap/app.php

# Setp 4: 创建配置文件
mkdir config
cp vendor/dingo/api/config/api.php config/

# Step 5: 修改routes.php

正常的话，可以测试了：
http://lumen.test.com/api/stats

```


