SQL injection exists in ibos Office OA v4.5.5

official website:http://www.ibos.com.cn/

version:v4.5.5

 Function point: Integrated office = "Recruitment management =" Contact record = "Export

 ![WPS图片(1)](https://github.com/spcck/cve/assets/126246514/c8c9c399-45af-4514-ba29-3b8664f28db1)
POC

Route: r=recruit/contact/export&contactids=x

The injection parameter contactids exists

Successfully burst the database name by reporting an error injection

![WPS图片(2)](https://github.com/spcck/cve/assets/126246514/f47f92b5-1a55-4aac-8226-bbb9d7a43823)

Find the actionExport() method, which accepts only one parameter, contactids, and then fetchAll() under model to execute the SQL statement.

![WPS图片(3)](https://github.com/spcck/cve/assets/126246514/73891461-9928-4ea0-9838-fb35744b6caa)

Fetchall() is still some data processing operation.

![WPS图片(4)](https://github.com/spcck/cve/assets/126246514/0ef8862a-ac6f-453a-b501-f309472b03b1)
