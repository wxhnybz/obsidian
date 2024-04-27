通常是在根目录下建立一个api文件夹
创建一个request.js

```
import axios from 'axios'
```
利用axios对象的方法create，去创建一个axios实例
requests就是axios需要配置
```
const request = axios.create(
{
baseURL :'/api'.
timeout:3000
}
)

```