1️⃣ What is PostgreSQL?
PostgreSQL একটি ওপেন সোর্স রিলেশনাল ডেটাবেজ ম্যানেজমেন্ট সিস্টেম। এটি একটি স্কিমা-নির্ভর ডেটাবেজ ম্যানেজমেন্ট সিস্টেম। এইটি মূলত অবজেক্ট-রিলেশনাল ডাটাবেজ ম্যানেজমেন্ট সিস্টেম (ORDBMS)।শক্তিশালী কমিউনিটি সাপোর্ট থাকা বিধায় প্রতিনিয়ত আধুনিক ফিচার অ্যাড হচ্ছে। এটি SQL স্ট্যান্ডার্ড অনুসরণ করে। PostgreSQL ডেটা অ্যানালিটিক্স, ওয়েব অ্যাপ্লিকেশনে, ই-কমার্স, এবং বড় বড় এন্টারপ্রাইজ সিস্টেমে এটি ব্যবহার করা হয়ে থাকে।

2️⃣ What is the purpose of a database schema in PostgreSQL?

সাধারণত বিভিন্ন ডাটাবেজ অবজেক্টের জন্য একটি namespace or  logical container হিসেবে কাজ করে থাকে।  এটি organization and grouping  হবার কারণে বিভিন্ন ডাটাকে যৌক্তিকভাবে একটি ডাটাবেজের মধ্যে গ্রুপ করতে সাহায্য করে থাকে।  ডাটা ব্যাকআপ এর ক্ষেত্রে কার্যকর ভূমিকা রেখে থাকে।  ইটস ইম্প্রোভ কোড রিডেবিলিটি।  তাছাড়া এটি Naming Conflicts দূর করার ক্ষেত্রে কার্যকর ভূমিকা রেখে থাকে। 

3️⃣ Explain the Primary Key and Foreign Key concepts in PostgreSQL.

Primary key সাধারণত একটি unique ID যা মূলত ডাটার মূল ইডেন্টিফায়ার হিসেবে কাজ করে থাক। Primary key কখনো NULL হতে পারে না প্রতিটি সারির জন্য Primary key মাস্ট থাকা লাগে।  এর প্রধান উদ্দেশ্য হলো প্রতিটি ডাটার রেকর্ডকে শনাক্ত করা।
কোনো এক টেবিল এর Primary Key  যদি আরেক টেবিলএ সম্পর্ক স্থাপন বা ডাটা পাবার জন্য যদি আরেকটি টেবিল এ উপস্থাপন করা হয়ে থাকে তখন তাকে Foreign Key বলে। Foreign Key NULL হতে পারে।  একাধিক Foreign Key থাকতে পারে এবং ডুপ্লিকেট থাকতে পারে।  

4️⃣ What is the difference between the VARCHAR and CHAR data types?

VARCHAR এবং চার দুইটি টেক্সট ডাটা ধারণ করার জন্য use করা হয়ে থাকে। CHAR সাধারণত নিদৃষ্ট দৈর্ঘ্যএর হয়ে থাকে অন্যদিকে VARCHAR পরিবর্তনশীল দৈর্ঘ্য হয়ে থাকে। CHAR এ প্যাডিং হয়ে থাকে অন্যদিকে VARCHAR কোনো প্যাডিং হয় না। CHAR বেটার ফর যখন সব ডাটার দৈর্ঘ্য সর্বদা একই থাকে।  VARCHAR বেটার ফর যখন ডাটার দৈর্ঘ্য পরিবর্তিত হতে পারে।

8️⃣ Explain the purpose of the WHERE clause in a SELECT statement.

JOIN অপারেশন সাধারণত ডাটাবেস এর বিভিন্ন টেবিল হতে ডাটা একত্রিত করে থাকে। সাধারণত এটির মূল কাজ হলো ডাটার Relationships তৈরী করা।   রিলেশনাল ডাটাবেসে এ ডুপ্লিকেশন এড়াতে এটি গুরুত্ব পূর্ণ ভূমিকা রেখে থাকে।  Complex Queries এর ক্ষেত্রে কার্যকর ভূমিকা রেখে থাকে। 

```sql
EmployeeID	Name	DepartmentID
1	Rohim	101
2	korim	102
3	solim	101
4	jahid	NULL
5	rubina	103
```

```sql
DepartmentID	DepartmentName
101	HR
102	Finance
103	IT
104	Marketing
```

```sql
SELECT
    E.Name,
    D.DepartmentName
FROM
    Employees E
INNER JOIN
    Departments D ON E.DepartmentID = D.DepartmentID;
```

এখানে INNER JOIN এর মাধ্যমে দুইটি টেবিল হতে Name এন্ড DepartmentName নিয়ে JOIN এর মাধ্যমে আর একটি টেবিল এ Name এন্ড DepartmentName দেখানো হয়েছে 

```sql
Name 	DepartmentName
রহিম	HR
করিম	Finance
সলিম	HR
রুবিনা	IT
```
```sql
SELECT s.common_name
FROM species s
LEFT JOIN sightings si ON s.species_id = si.species_id
WHERE si.species_id IS NULL;
```
এখানে LEFT JOIN ব্যবহার করা হয়েছে যাতে যেসব রেঞ্জার কোনো সাইটিং করেনি তাদেরও যাতে দেখানো যায়।