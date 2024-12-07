---
title: 初探MongoDB
published: 2024-05-10
description: 探讨了MongoDB和MySQL的区别，以及MongoDB的文档结构。
tags: [MongoDB, MySQL, JSON, Database]
category: Back-end
draft: false
---

#NoSQL #mongoDB #SQL #JSON 
# 和MySQL有什么不同？

![[Pasted image 20240509164616.png]]

MongoDB 不使用传统的表格结构，而是使用称为“文档”的数据结构，这使得嵌入文档和数组变得非常容易，非常适合用来处理与帖子和评论相关的图片数据。

MongoDB 是一种非关系型数据库，其数据存储方式和关系型数据库有很大的不同。在 MongoDB 中，数据以文档（document）的形式存储，这些文档类似于 JSON 对象（BSON,Binary JSON)。每个文档可以有不同的字段（field），这就允许文档在结构上具有很大的灵活性。

# 怎么理解MongoDB？

> 提问： MongoDB是不是就相当于一个实体一个文件？就例如一个人有驾照，可以包含一个驾照栏位，那么可以加一行 driver_license:true，另一个人没有驾照，就可以没有这个栏位，但他有日语证书，就可以加一行JLPT: "N1"这样？

GPT：是的，你的理解基本正确。在你的例子中，如果使用 MongoDB 存储用户信息，每个用户的文档可以根据具体情况包含不同的字段：

```JSON
{
  "_id": ObjectId("507f191e810c19729de860ea"),
  "name": "Alice",
  "email": "alice@example.com",
  "driver_license": true
}

```

```JSON
{
  "_id": ObjectId("507f191e810c19729de860eb"),
  "name": "Bob",
  "email": "bob@example.com",
  "JLPT": "N1"
}
```
### MongoDB 文档的特点

1. **灵活性**：如你所见，不同的文档可以有不同的字段。这使得 MongoDB 特别适合于那些数据结构可能随时间变化或不一致的应用。
    
2. **无模式（Schema-less）**：MongoDB 是无模式的，这意味着你不需要预先定义文档结构。你可以随时添加新的字段，或者在不同的文档中使用不同的字段集。
    
3. **扩展性**：MongoDB 支持水平扩展，通过分片技术可以在多台服务器之间分散数据，这使得它非常适合大数据量和高并发的应用。
    
4. **索引和查询性能**：尽管文档的结构可能不一致，MongoDB 仍然可以对任何字段建立索引，这保证了即使在包含大量文档和复杂查询的情况下也有良好的性能。

### 使用场景

- **内容管理系统**：在内容管理系统中，不同类型的内容可能有不同的属性，MongoDB 的灵活性允许轻松处理这种多样性。
- **电子商务应用**：在电子商务平台，每个产品可能有不同的属性集，MongoDB 可以有效地存储这种多样化的产品信息。
- **个性化服务**：对于需要存储大量个性化用户偏好或配置的服务，MongoDB 的文档模型提供了一个非常合适的解决方案。

总的来说，MongoDB 提供了高度的灵活性和扩展性，非常适合那些需求不断变化或者数据结构不一致的现代应用程序。

# 实操环节

> 默认端口：27017

| MYSQL       | MongoDB                               |
| ----------- | ------------------------------------- |
| Database    | Database                              |
| Table       | Collection                            |
| Row         | <font color="#ffc000">Document</font> |
| Column      | Field                                 |
| Index       | Index                                 |
| Primary Key | <font color="#ff0000">\_id\_</font>   |
| join        | $look_up                              |

