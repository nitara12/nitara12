- 👋 Hi, I’m @nitara12
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...



# <a href="https://www.ilion.com/">Agen Bola</a>
## Technology stack

react@16.0 + redux@3.7.2 + react-router@3.2.0 + webpack@3.10.0 + axios@0.18.0 + less@2.7.1 + antd@3.1.3



## Project introduce


```
git clone --depth 1 https://github.com/duxianwei520/react.git  

cd react 

npm install 

npm start 
```
Open another node service to open the mock interface service,if you don't start the mock interface service, you won't login into the inner page
```
npm run mock 
```
#### Notice

If you wan to experience the chatroom, you need to start socket service first, so you need to run another node service like this
```
npm run chat
```
and if you want to publish your app, use the following line of commands
```
npm run build 

```

This is the basic structure of the data returned by the server.

```
{
  data: {
    totalCount: 100,
    currentPage: 1,
    pageSize: 10,
    'list': [
    ],
  },
  msg: '',
  status: 1,
}
```
All asynchronous request returns will be processed by 'ajax.js' in configs folder. If there is no problem with the request, the `status` return value is `1`;
If the request is wrong, such as a parameter error or other error, the `status` return value is `0`;
If the status value is `-1`, indicating that the login timed out, then the login will pop up.
These parameters can be adjusted according to the actual situation, and the error message or successful prompt information is returned in `msg`.
The current project integrates basic user management, role management, module management and other basic rights management functions. The small partners must start `npm run mock` at the same time to see 



## Description 

>  development environment: win10  Chrome 63.0.3239.132  nodejs 8.7.0


>  If you have any questions, please mention them directly in the Issues. I will answer in the first time, or you find that the problem has a very good solution, welcome PR

### Cancel http request example：
```
import axios from 'axios'
const axiosHandle = axios.CancelToken.source()

login(){
  this.props.dispatch(fetchLogin(values, (res) => {},(error)=>{},axiosHandle)
  setTimeout(() => {
    axiosHandle.cancel('cancel handle')
  }, 3000)
}
