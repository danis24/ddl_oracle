#Explanation For DDL Oracle

##DDL Create
```
create table users{
    id int primary key auto_increment,
    first_name varchar(30),
    last_name varchar(30),
    email varchar(50) unique,
    username varchar(50) unique,
    password varchar(75),
    created_at timestamp,
    update_at timestamp
}
```

##DDL Alter
    ###Add columns
        -> Single
            ```
            ALTER TABLE users ADD address varchar2(45);
            ```
        -> multiple
            ```
            ALTER TABLE users ADD (contact varchar2(12), company varchar2(50));
            ```
    ###Modify columns
        ->Single
            ```
            ALTER TABLE users MODIFY contact varchar2(20);
            ```
        ->multiple
            ```
            ALTER TABLE users MODIFY (address varchar2(100), company varchar2(30));
            ```
    ###Rename columns
        ```
        ALTER TABLE users RENAME COLUMN contact TO phone;
        ```
    ###Rename Table
        ```
        ALTER TABLE users RENAME TO updated_users;
        ```
    ###Drop columns
        ```
        ALTER TABLE users DROP COLUMN company;
        ```

##DL Drop
    ```
    DROP table users PURGE;
    ```
##DDL Truncat
    ```
    TRUNCATE TABLE users PRESERVE MATERIALIZED VIEW LOG;
    TRUNCATE TABLE users;
    ```
##Perhari
    ```
    SELECT * FROM users WHERE created_at = now();
    ```

##Perbulan
    ```
    SELECT * FROM users WHERE MOUNTH(created_at) = '02' GROUP_BY created_at;
    ```

##Pertahun
    ```
    SELECT * FROM users WHERE YEAR(created_at) = '2017' GROUP_BY MOUNTH(created_at);
    ```
