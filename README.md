Solution name: MVCWithAdo

Author: Byeongho Hwang

Explanation: This is a demo project that uses .NET MVC framework to showcase
             accessing DB using ADO.NET framework. DB is not directly created
             inside the project. Instead, I created DB on MS SQL server management studio.
             Sql query is below. The tutorial is given in the link below:
             https://www.c-sharpcorner.com/UploadFile/francissvk/crud-operations-in-Asp-Net-mvc-using-ado-net/
             
             On the index page, when the application is fired, it shows two records I put
             into DB thru sql query. Also, you can do all CRUD operations like
             1) add a student
             2) edit student details
             3) delete a student
             4) display all students
             
             When there is a update, it will affect not only the application's DB view but also
             the original DB itself.
             
             
             
[sql query]             
             
SET ANSI_NULLS ON  
GO  
  
SET QUOTED_IDENTIFIER ON  
GO  
  
SET ANSI_PADDING ON  
GO  
  
IF OBJECT_ID(N'dbo.tblStudent', N'U') IS NOT NULL  
   DROP TABLE [dbo].[tblStudent];  
GO

CREATE TABLE [dbo].[tblStudent](  
  [student_id][int] IDENTITY(1, 1) NOT NULL,  
  [student_name][varchar](50) NOT NULL,  
  [student_age][int] NOT NULL,  
  [student_gender][varchar](6) NOT NULL,  
  CONSTRAINT[PK_tblStudent] PRIMARY KEY CLUSTERED(  
    [student_id] ASC  
  ) WITH(PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON[PRIMARY]  
) ON[PRIMARY]  
  
GO  
  
SET ANSI_PADDING OFF  
GO 


Insert into tblStudent (student_age, student_gender, student_name)
	values (12, 'male', 'Brian')
	, (19, 'female', 'Cathy')
