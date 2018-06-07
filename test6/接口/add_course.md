# 接口：add_course  [返回](../README.md)
用例： [课程管理](../用例/课程管理.md)

- 权限：
    老师：只有老师用户才可以调用该API

- 功能：
    为供选择的课表做设置。

- API请求地址：
   接口基本地址/v1/api/add_course

- 请求方式 ：
    POST
    
- 请求实例： 

        {
            "teacher_id":"123456"
            "teacher_name":"赵卫东"
            "total":"6"
            "data"[{
                "course_id": "101"
                "course_name": "信息系统分析与设计"
                "open_class_college ": "信息科学与工程学院"
                "open_class_major ": "软件工程"
            },
            {
             ...其他课程
            ]
          "type" :"老师"
        }


- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |teacher_id|老师用户的ID号。对应表TEACHERS.TEACHER_ID的值|
  |teacher_name|老师的用户名| 
  |total|选课的总数，小于等于课程总数|
  |data|所有的课程信息数组|
  |course_id|课程ID。对应表COURSES.COURSE_ID的值|
  |course_name|课程的名称|
  |open_class_college|开课学院|
  |open_class_major |开课专业|
  |type|用户类型。老师或学生|
  
- 返回实例：

        {         
            "status": true,
            "info": null,    

        }
 
- 返回参数说明： 
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
