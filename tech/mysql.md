    
启动
```docker
sudo docker run \
        --name mysql_3807 \
        --restart=always \
        -e MYSQL_ROOT_PASSWORD=root \
        -p 3807:3306 \
        -d \
        -v /opt/data/docker/mysql/data_3306_1:/var/lib/mysql \
        mysql:5.6 \
        --character-set-server=utf8mb4 --collation-server=utf8mb4_unicode_ci

```

```bash
mysql -u root -p --port=3807 -h 127.0.0.1    
```

```mysql
UPDATE  abbonamento
SET     punti = IF(tipo = 'punti', punti - 1, punti),
        bonus = IF(tipo <> 'punti', bonus - 1, bonus)
WHERE   id = 17
```

```mysql

DROP FUNCTION IF EXISTS replace_num; 
DELIMITER //
CREATE FUNCTION `replace_num`(input TEXT)
  RETURNS TEXT
  BEGIN
    DECLARE output TEXT DEFAULT '';
    DECLARE iterator INT DEFAULT 1;
    WHILE iterator < (LENGTH(input) + 1) DO
      IF SUBSTRING(input, iterator, 1) IN (1,2,3,4,5,6,7,8,9,0)
      THEN
        SET output = CONCAT(output, SUBSTRING(input, iterator, 1) % 3 % 2);
      ELSE
        SET output = CONCAT(output, SUBSTRING(input, iterator, 1));
      END IF;
      SET iterator = iterator + 1;
    END WHILE;
    RETURN output;
  END //
DELIMITER ;
SELECT replace_num('18601878ssss929');

#查看表大小
select table_name,CONCAT(round(data_length/1024/1024/1024,2), 'G') from information_schema.tables where  table_schema="jsqb" and table_name like "tb_%" order by data_length desc

```

- Innodb性能优化之参数设置 http://blog.bruceding.com/233.html
- Dumping and importing from/to MySQL in an UTF-8 safe way https://makandracards.com/makandra/595-dumping-and-importing-from-to-mysql-in-an-utf-8-safe-way


提高导入性能
- --innodb_buffer_pool_size=1512m --innodb_log_buffer_size=100m --innodb_flush_log_at_trx_commit=2
```bash

#复制数据库

  mysqldump --opt --single-transaction -uroot -proot -h pt_mysql tmp_jsqb_assist | mysql -uroot -proot -h pt_mysql -C jsqb_assist

#导出数据样本

  mysqldump -alv --opt --single-transaction -uroot -proot -h pt_mysql tmp_jsqb -r jsqb.sql >> test.log
  
#导入数据

  mysql -v -uroot -proot -h pt_mysql jsqb < jsqb.sql

#导出生产数据

  mysqldump --opt --single-transaction -ujsqb_read  -p -h $MYSQL_HOST  jsqb -r jsqb.sql




