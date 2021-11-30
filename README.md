# Process-Eniginner-Work-Detil
Summray:

1.梳理主要日常工作
2.梳理产品担当工作内容-重点
3.梳理工艺调试内容
4.其他工作方面内容内容


Part1:日常主要工作

1.主要作为产品担当对应新产品干法刻蚀段工艺导入
2.设备机况处理，量产品刻蚀段不良调查改善，确保产品良率。总结异常经验，输出调查改善报告
3.干法刻蚀主设备及附属设备的产品过货参数监控，确认产品各项参数是否正常，异常时及时作出改善
4.刻蚀设备的各类部件清洗维修出厂/返厂管理，进度追踪。设备备件清洗二元化导入流程追踪，结案报告输出及后续二元化运行状况监控；
5.科室部分标准流程文件，SOP撰写及其它领导安排工作事项；

Part2：新产品导入事项总结

1.新产品开案
  1)确认搭载平台(指前层Photo Mask使用何种平台)，确认膜层结构（指采用多少道Mask？CNT EBA是否合并为EBI Mask？采用单层SD还是双层（对应为单层PLN或双层  PLN）CNT Ashing是否Skip？），确认工艺Flow（指整个工艺流程的配置，Doping方式？Anode搭载方式？）
  2)工艺风险点评估-SD是否容易断线？设计方面是否存在特殊电路设计导致刻蚀产生不良？
  3)CD Bias确认，CD Bias=|DICD-FICD|
  
2.CP文件确认及设备工艺参数表建立
  1)确认各layer主刻蚀步骤Recipe为新品现行最优刻蚀条件
  2)CP绑定过货设备确认
  3)设备Recipe主刻蚀步骤，AT步骤参数确认
  4)CP文件量测机台抽检频率确认

3.DV Lot投入事项
  1)DV为先行测试批，确认先行批在各设备过货参数是否正常，AOI是否正常，抽片建立CD量测设备Recipe并进行Offset确认
  2)抽片进行FIB 确认各膜层CD Bias及Taper形貌、数据是否正常
  3)DV阶段CTQ（CD/CD Bias，Taper等数据）数据数据收集及异常调查
  4)
5.导入量产
  1)DV阶段各项准备工作完成，产品导入量产并出货至客户
  2)定期收集并监控CTQ数据，调查改善产品量产过程中的异常情况
  3)直至出货量达标，产品不再进行投产，该产品生命周期到此结束，等待有订单量后下一次投产；




MyAPP
package com.ysLearning.domain;

import org.apache.ibatis.io.Resources;
import org.apache.ibatis.session.SqlSession;
import org.apache.ibatis.session.SqlSessionFactory;
import org.apache.ibatis.session.SqlSessionFactoryBuilder;

import java.io.IOException;
import java.io.InputStream;
import java.util.List;

public class MyApp {

    public static void main(String[] args) throws IOException {
        //访问mybatis，读取student数据
        //1.定义mybatis主配置文件的名称，从类路径的根开始（target/classes）
        String config="mybatis.xml";
        //2.读取config代表的xml文件
        InputStream in= Resources.getResourceAsStream(config);
        //3。创建sqlSessionFactoryBuilder对象
        SqlSessionFactoryBuilder builder=new SqlSessionFactoryBuilder();
        //4.创建sqlSessionFactory对象
        SqlSessionFactory factory;
        factory = builder.build(in);
        //5.[重要]获取SqlSession对象，从SqlSessionFactory中获取
        SqlSession sqlSession=factory.openSession(true);
        //6.[重要]指定要执行的sql语句的标识-sql映射文件中的namespace+"."+标签的id值
        String sqlid="com.ysLearning.dao.StudentDao.selectStudent";
        //7.执行sql语句，通过sqlid找到语句
        List<Student> studentList= sqlSession.selectList(sqlid);
        //8.输出结果
        studentList.forEach(stu->System.out.println(stu));

        sqlSession.close();
    }
}





MyBatisUtils

package com.ysLearning.domain;

import org.apache.ibatis.io.Resources;
import org.apache.ibatis.session.SqlSession;
import org.apache.ibatis.session.SqlSessionFactory;
import org.apache.ibatis.session.SqlSessionFactoryBuilder;

import java.io.IOException;
import java.io.InputStream;
import java.util.List;

public class MyApp {

    public static void main(String[] args) throws IOException {
        //访问mybatis，读取student数据
        //1.定义mybatis主配置文件的名称，从类路径的根开始（target/classes）
        String config="mybatis.xml";
        //2.读取config代表的xml文件
        InputStream in= Resources.getResourceAsStream(config);
        //3。创建sqlSessionFactoryBuilder对象
        SqlSessionFactoryBuilder builder=new SqlSessionFactoryBuilder();
        //4.创建sqlSessionFactory对象
        SqlSessionFactory factory;
        factory = builder.build(in);
        //5.[重要]获取SqlSession对象，从SqlSessionFactory中获取
        SqlSession sqlSession=factory.openSession(true);
        //6.[重要]指定要执行的sql语句的标识-sql映射文件中的namespace+"."+标签的id值
        String sqlid="com.ysLearning.dao.StudentDao.selectStudent";
        //7.执行sql语句，通过sqlid找到语句
        List<Student> studentList= sqlSession.selectList(sqlid);
        //8.输出结果
        studentList.forEach(stu->System.out.println(stu));

        sqlSession.close();
    }
}



MyAppWithUtils:
package com.ysLearning.domain;

import org.apache.ibatis.io.Resources;
import org.apache.ibatis.session.SqlSession;
import org.apache.ibatis.session.SqlSessionFactory;
import org.apache.ibatis.session.SqlSessionFactoryBuilder;

import java.io.IOException;
import java.io.InputStream;
import java.util.List;

public class MyApp {

    public static void main(String[] args) throws IOException {
        //访问mybatis，读取student数据
        //1.定义mybatis主配置文件的名称，从类路径的根开始（target/classes）
        String config="mybatis.xml";
        //2.读取config代表的xml文件
        InputStream in= Resources.getResourceAsStream(config);
        //3。创建sqlSessionFactoryBuilder对象
        SqlSessionFactoryBuilder builder=new SqlSessionFactoryBuilder();
        //4.创建sqlSessionFactory对象
        SqlSessionFactory factory;
        factory = builder.build(in);
        //5.[重要]获取SqlSession对象，从SqlSessionFactory中获取
        SqlSession sqlSession=factory.openSession(true);
        //6.[重要]指定要执行的sql语句的标识-sql映射文件中的namespace+"."+标签的id值
        String sqlid="com.ysLearning.dao.StudentDao.selectStudent";
        //7.执行sql语句，通过sqlid找到语句
        List<Student> studentList= sqlSession.selectList(sqlid);
        //8.输出结果
        studentList.forEach(stu->System.out.println(stu));

        sqlSession.close();
    }
}
