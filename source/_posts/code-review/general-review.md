---
layout: post
title: 我的代码审查实践(25分钟看完系列)
category: 代码审查
keywords: null
date: 2018-04-28 16:09:02
---

## 阅读前

1. 阅读这篇文章后你能学到什么?

我的代码审查实践

2. 你将用多少时间来阅读这篇文章?

25 分钟

## 目标

* **分享知识**
* **提高代码的可读性**

## 例子

### 一般错误

#### 不必要的额外的逻辑层

```
  function getUserAccount(){
   if(Auth.isLogin()){
     return Auth::user();
   }else{
     throw Error('get user when user is not authorized')
   }
  }
```

**错误**

- 程序员需要额外的一层才能知道程序会抛出异常**如果用户不满意**。

```
  function getUserAccount(){
  if(!Auth.isLogin()){
    throw Error('get user when user is not authorized')    
  }
    return Auth::user();
  }
```

**改进**

- 程序员知道调用者必须确保用户**需要确保用户需要登录**才能正确地调用**这个功能

#### Retrieve array of items from indexed data object when already have indexed keys

```
function getUsers(usersById,targetUserIds){
  return _.filter(usersById, user =>
    targetUserIds.includes(
      user.id
    )
  );
}
```

**错误**

- low performance and readability

```
function getUsers(usersById,targetUserIds){
  return targetUserIds.map(targetUserId=>usersById[targetUserId])
}
```

**改进**

- better performance and readability



#### Unnecessary extra logic layer when processing overloading function

```
  function getUser(idOrIds){
    let relatedUser;
    let predefinedUsers = [
      {"name":"jeff",age:"20",id:"id1"},
      {"name":"mandy",age:"20",id:"id2"},


    ];
     if(Array.isArray(idOrIds)){
       return  predefinedUsers.filter(user=>idOrIds.includes(user.id));
     }else{
       return  predefinedUsers.filter(user=>user.id==idOrIds);
     }
  }
```

**错误**

- Should seperation the type conversion and only have one process logic

**改进**

```
  function getUser(idOrIds){
    let relatedUser;
    let predefinedUsers = [
      {"name":"jeff",age:"20",id:"id1"},
      {"name":"mandy",age:"20",id:"id2"},


    ];
     if(!Array.isArray(idOrIds)){
       idOrIds = [idOrIds];
     }
    //One processing logic only
     let results =   predefinedUsers.filter(user=>idOrIds.includes(user.id));

     if(Array.isArray(idOrIds)){
      return results;
     }else{
       return results[0];
     }

  }
```
