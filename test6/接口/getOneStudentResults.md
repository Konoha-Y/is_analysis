# 接口：getOneStudentResults  [返回](../README.md)
用例： [查看成绩](../用例/查看成绩.md) ,[评定成绩](../用例/评定成绩.md)

- 权限：
    学生：只能查看自己的成绩，即接口参数student_id必须等于登录学生的student_id 老师：可以查看所有学生的成绩。

- 功能：
    返回一个学生的所有实验成绩和实验评价。

- API请求地址：
   接口基本地址/v1/api/getOneStudentResults/<student_id>

- 请求方式 ：
    GET

- 请求参数说明:

|参数名称|说明|
|:---------:|:----------|
|student_id | 学生的学号|

- 返回实例：

        {         
               "status": true,
               "info": null,    
               "student_id": "201510414126", 
               "github_username": "Y-konoha", 
               "class": "软件(本)15-1", 
               "name": "姚启迪", 
               "total": 6,
               "avg_result":87.5,       
               "data": [
                   {
                   "test_id":1,
                   "web_exists": true, 
                   "result": 95, 
                   "memo":"本实验流程准确，条理清晰",
                   "update_date": "2018-05-02 13:48:55"
                   }, 
                   {
                   ...其他实验
                   }
               ] 
           }

- 返回参数说明：

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |STUDENT_ID|学号|
  |GITHUB_USERNAME|学生的GITHUB用户名|
  |CLASS|班级|
  |NAME|真实姓名|
  |TOTAL|实验总数|
  |AVG_RESULT | 学所有成绩的平均分|
  |DATA|所有实验的成绩和评语|
  |RESULT|实验1的成绩|
  |TEST_ID|实验编号|
  |WEB_EXISTS|本实验的GitHub网页是否存在|
  |RESULT|本实验成绩，可以为空，为空表示没有批改，没有批改的实验不入平均成绩，为0分则要计入平均成绩，所以成绩为空和为0是不一样的。|
  |MEMO|本实验老师的评价，可以为空|
  |UPDATE_DATE|本实验老师的批改日期，可以为空|
