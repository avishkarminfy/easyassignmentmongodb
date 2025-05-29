# Easy Assignment Mongodb<br></br>
1. List All Products in the "Electronics" Category:<br></br>
# Command:<br></br>
db.products.aggregate([<br></br>
{<br></br>
$match: { category: "Electronics" }<br></br>
}<br></br>
])<br></br>
# Output:<br></br>
{<br></br>
_id: ObjectId('68383a1c402b38d32a2df653'),<br></br>
name: 'Laptop Pro',<br></br>
category: 'Electronics',<br></br>
price: 1200,<br></br>
quantity: 10,<br></br>
tags: [<br></br>
'computer',<br></br>
'portable',<br></br>
'work'<br></br>
],<br></br>
date_added: 2023-01-15T10:00:00.000Z,<br></br>
supplier: {<br></br>
name: 'TechGlobe',<br></br>
location: 'USA'<br></br>
}<br></br>
}<br></br>
<br></br>
{<br></br>
_id: ObjectId('68383a1c402b38d32a2df654'),<br></br>
name: 'Wireless Mouse',<br></br>
category: 'Electronics',<br></br>
price: 25,<br></br>
quantity: 100,<br></br>
tags: [<br></br>
'peripheral',<br></br>
'computer',<br></br>
'wireless'<br></br>
],<br></br>
date_added: 2023-02-01T11:30:00.000Z,<br></br>
supplier: {<br></br>
name: 'GadgetPro',<br></br>
location: 'China'<br></br>
}<br></br>
}<br></br>
{<br></br>
_id: ObjectId('68383a1c402b38d32a2df655'),<br></br>
name: 'Mechanical Keyboard',<br></br>
category: 'Electronics',<br></br>
price: 75,<br></br>
quantity: 50,<br></br>
tags: [<br></br>
'peripheral',<br></br>
'computer',<br></br>
'mechanical'<br></br>
],<br></br>
date_added: 2023-01-20T14:00:00.000Z,<br></br>
supplier: {<br></br>
name: 'TechGlobe',<br></br>
location: 'USA'<br></br>
}<br></br>
}<br></br>
{<br></br>
_id: ObjectId('68383a1c402b38d32a2df659'),<br></br>
name: 'Smartwatch',<br></br>
category: 'Electronics',<br></br>
price: 199,<br></br>
quantity: 25,<br></br>
tags: [<br></br>
'wearable',<br></br>
'gadget',<br></br>
'portable'<br></br>
],<br></br>
date_added: 2023-04-01T12:00:00.000Z,<br></br>
supplier: {<br></br>
name: 'GadgetPro',<br></br>
location: 'China'<br></br>
}<br></br>
}<br></br>
{<br></br>
_id: ObjectId('68383a1c402b38d32a2df65c'),<br></br>
name: 'Bluetooth Speaker',<br></br>
category: 'Electronics',<br></br>
price: 80,<br></br>
quantity: 60,<br></br>
tags: [<br></br>
'audio',<br></br>
'portable',<br></br>
'wireless'<br></br>
],<br></br>
date_added: 2023-02-25T17:00:00.000Z,<br></br>
supplier: {<br></br>
name: 'SoundWave',<br></br>
location: 'USA'<br></br>
}<br></br>
}<br></br>
<br></br>
# 2. Count Products per Category:<br></br>
# Command:<br></br>
db.products.aggregate([<br></br>
{<br></br>
$group: {<br></br>
_id: "$category",<br></br>
count: { $sum: 1 }<br></br>
}<br></br>
}<br></br>
])<br></br>
<br></br>
# Output Screenshot:<br></br>
&lt;img width="637" alt="image" src="https://github.com/user-attachments/assets/19a9761e-0bc0-4ce0-96e1-28a3f4f8ba62" /&gt;<br></br>
<br></br>
# 3. Product Names and Prices, Sorted by Price (Descending):<br></br>
# Command:<br></br>
db.products.aggregate([<br></br>
{<br></br>
$project: {<br></br>
_id: 0,<br></br>
name: 1,<br></br>
price: 1<br></br>
}<br></br>
},<br></br>
{<br></br>
$sort: {<br></br>
price: -1<br></br>
}<br></br>
}<br></br>
])<br></br>
<br></br>
# Output:<br></br>
{<br></br>
name: 'Laptop Pro',<br></br>
price: 1200<br></br>
}<br></br>
{<br></br>
name: 'Espresso Machine',<br></br>
price: 250<br></br>
}<br></br>
{<br></br>
name: 'Smartwatch',<br></br>
price: 199<br></br>
}<br></br>
{<br></br>
name: 'Bluetooth Speaker',<br></br>
price: 80<br></br>
}<br></br>
{<br></br>
name: 'Mechanical Keyboard',<br></br>
price: 75<br></br>
}<br></br>
{<br></br>
name: 'Denim Jeans',<br></br>
price: 60<br></br>
}<br></br>
{<br></br>
name: 'Leather Wallet',<br></br>
price: 45<br></br>
}<br></br>
{<br></br>
name: 'Yoga Mat',<br></br>
price: 30<br></br>
}<br></br>
{<br></br>
name: 'Wireless Mouse',<br></br>
price: 25<br></br>
}<br></br>
{<br></br>
name: 'Cotton T-Shirt',<br></br>
price: 20<br></br>
}<br></br>
