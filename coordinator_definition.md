## �����������ĵ�˵��
`akkaflow`�ĵ���������`coordinator`��������ʱ�䴥������������������ʱ�䴥��������Linux�ϵ�crontab���ܣ�ָ��ĳ��ʱ��㴥��ĳ������`workflow`��������������������ĳ������������ɴ�����һ����������`akkflow`��`coordinator`�ȿ�������ʱ��������������Ҳ���Զ���������á����⣬�������п����ò��������������ò��������ϵͳ�������ṩ�������Ĺ�����ʹ�á�

#####һ���������ļ�����ʾ��
```xml
<coordinator name="coor1_2" start="2016-09-10 10:00:00" end="2017-09-10 10:00:00" id="0002">    
    <trigger>
        <cron config="* * * * * *"/>
        <depend-list>
          <depend wf="wf_1" />
          <depend wf="wf_2" />
        </depend-list>
    </trigger>
    <workflow-list>
      <workflow path="wf_3"></workflow>
      <workflow path="wf_4"></workflow>
    </workflow-list>
    <param-list>
        <param name="yestoday" value="${time.today|yyyy-MM-dd|-1 day}"/>
        <param name="lastMonth" value="${time.today|yyyyMM|-1 month}"/>
        <param name="yestoday2" value="${time.yestoday|yyyy/MM/dd}"/>
        <param name="hdfs_dir" value="hdfs:///user/kent/log/${yestoday2}/*"/>
    </param-list>
</coordinator>
```
###&lt;coordinator/&gt;
�������������ö�����`coordinator`��ǩ��,`coordinator`��Ϊ�����ı�ǩ��
####* ����
`name`��������ƣ�������ʶΨһ�Ĺ�����
