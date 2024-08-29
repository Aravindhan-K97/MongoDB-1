# MongoDB-1 

`This Repository contains a Document file.`  

## To view the Document file :

- Click on the `MongoDB_Task_1.docx` file above to `Download` and view the file in which I've attached the `Screenshot` below each `Query` respectively.


## <h2 align="left">Programming Language Used :</h2>

<div align="left">
  <img src="https://img.shields.io/badge/MongoDB-%234ea94b.svg?style=for-the-badge&logo=mongodb&logoColor=white" height="40" alt="mongod logo"  />
  <img width="40" />
  </div>


## <h2 align="left">Programming Tool Used :</h2>

<div align="left">
  <img src="https://www.svgrepo.com/show/303232/mongodb-logo.svg" height="100" alt="mongodb logo"  />
  <img width="50" />
  </div>

## MONGODB :

*MongoDB is built on a scale-out architecture that has become popular with developers of all kinds for developing scalable applications with evolving data schemas.*

*As a document database, MongoDB makes it easy for developers to store structured or unstructured data. It uses a JSON-like format to store documents. This format directly maps to native objects in most modern programming languages, making it a natural choice for developers, as they don’t need to think about normalizing data. MongoDB can also handle high volume and can scale both vertically or horizontally to accommodate large data loads.*

*MongoDB was built for people building internet and business applications who need to evolve quickly and scale elegantly. Companies and development teams of all sizes use MongoDB for a wide variety of reasons.*

## Features :

  - Document Model
  - Deployment Options
  - Get Started Quickly
  - Fully Scalable
  - Find Community

## Execution of 10 Questions :

**Executed Queries for each Questions**

1. Find all the information about each products

```bash
db.products.find();
```

2. Find the product price which are between 400 to 800

```bash
db.products.find({‘product_price’:{$gte:400,$lte:800}});
```

3. Find the product price which are not between 400 to 600

```bash
db.products.find({‘product_price’:{$not:{$gte:400,$lte:600}}});
```

4. List the four product which are grater than 500 in price

```bash
db.products.find({‘product_price’:{$gt:500}}).limit(4);
```

5. Find the product name and product material of each products

```bash
db.products.find({},{‘product_name’:1,’product_material’:1});
```

6. Find the product with a row id of 10

```bash
db.products.find ({'id':'10'});
```

7. Find only the product name and product material

```bash
db.products.find ({},{'_id':0,'id':0,'product_price':0,'product_color':0});
```

8. Find all products which contain the value of soft in product material

```bash
db.products.find ({'product_material':'Soft'});
```

9. Find products which contain product color indigo and product price 492.00

```bash
db.products.find ({$and:[{'product_color':'indigo'},{'product_price':492}]});
```

10. Delete the products which product price value are same

```bash
db.products.aggregate([
{
$group: {
_id: '$product_price',
count: { $sum: 1 }
}
},
{
$match: {
count: { $gt: 1 }
}
}
]).forEach((e) => {
db.products.deleteMany ({ product_price: e._id });
});

```
