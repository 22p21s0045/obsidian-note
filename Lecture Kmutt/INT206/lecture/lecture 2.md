3/7/2024
[[INT206_05_TransactionManagement_Part1_02_2023.pdf]]
#tips
Truncate command is auto commit
#transaction
# Transaction control language
In the context of a **database**, a **transaction** is a **logical unit** that is independently executed for data retrieval or updates. Think of it as a “unit of work” within the database design environment. Let’s delve into the details:

## Defination
- A logical Unit of work
- Check state of data

## **Operations of a Transaction**:

- **Read (X)**: (<mark class="hltr-yellow">SELECT</mark>)
    - A **read operation** retrieves the value of **X** from the database and stores it in a buffer in the main memory.
    - This operation is used when a user wants to **view** content from the database without making any changes.
    - For example, checking an account balance involves a read operation on the user’s account balance.
- **Write (X)**: (<mark class="hltr-yellow">INSERT UPDATE DELETER</mark>)
    - A **write operation** updates the value in the database from the buffer in the main memory.
    - First, a **read operation** fetches the value into the buffer.
    - Then, changes (such as arithmetic operations) are made to it based on the user’s request.
    - Finally, the modified value is stored back in the database using a write operation.
    - For instance, when a user withdraws money, the account balance undergoes read and write operations.

![](https://i.imgur.com/3ctHvQZ.png)
- Inconsistent state (ค่ายังไม่นิ่ง)
- Partially commited (ส่วนที่ commit ได้ก็จะถูก Commit)
- ถ้า fail ก็จะ rollback อัตโนมัติ

<mark class="hltr-yellow">commit</mark>-> consistant -> new consistant state
<mark class="hltr-yellow">aborted</mark> -> rollback -> previous consistant state

## Properties of transaction 
- Atomicity : ต้นทางปลายทางเป็นชุดเดียวกัน
- Consistency : ข้อมูลเป็นเวอร์ชั่นล่าสุด
- Isolation : เวลากําลังทําอะไร transaction อื่นไม่ควรเข้ามายุ่งได้
- Durability : การันตีว่าข้อมูลนั้นเก็บลงไฟล์เรียบร้อย
![](https://i.imgur.com/pEHDVHw.png)
[ACID Explained: Atomic, Consistent, Isolated & Durable – BMC Software | Blogs](https://www.bmc.com/blogs/acid-atomic-consistent-isolated-durable/)

![](https://i.imgur.com/csbEQip.png)
- Buffer Manager จัดการข้อมูลที่ค้างอยู้ใน main memory 
- File manager -> access manager ->system manager


## [[Concurrency control]]
- รองรับปริมาณ transaction ให้ได้เยอะมากที่สุด
- ทําให้กวนกันน้อย
## Database Recovery
- พยายามให้มัน synกันได้ถ้า down ไป


