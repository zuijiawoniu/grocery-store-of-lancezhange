# 数据库

- 主键： 表的唯一索引，如 id int(10) not null primary key auto_increment;
- 索引： 索引能够加快检索速度（但其创建和维护也需时间，同时也占用一定空间）
    - 添加索引的方式： alter table TABLE_NAME add index INDEX_NAME (COL_NAME);
