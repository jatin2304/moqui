# setup for moqui
1. Installed  Java Development Kit (JDK 11; note: above versions were not supported)
2. Installed IntelliJ IDEA.
3. Setting Up Moqui for Development
        Step 1: Clone the Moqui Framework
            mkdir sandbox 
            cd moqui-sandbox
            Cloned the Moqui Framework repository using command:
            git clone -b master https://github.com/moqui/moqui-framework.git
        Step 2: Runtime Component initialization
            In the moqui-framework directory:
            cd moqui-framework
            Set up the default runtime directory using command:
            C:/sandbox/moqui-framework> ./gradlew getRuntime
        Step 3: Created  Moqui Component
            Created the ‘moqui-training’ component inside runtime/component.
        Step 4: Inside the component folder, created the necessary directories: screen, entity, service, data, script
        Step 5: Created a component.xml file with the appropriate name. In a 'component' element and provide name and version of moqui(3.0.0).
4. Setting Up MySQL for Moqui
        Step 1: Installed MySQL 8.0.32 
        Step 2: Installed JDBC Driver(MySQL Connector/J 8.0.32) and place the driver .jar file in runtime/lib.
        Step 3: Database creation
            Executed the following SQL commands in workbench to create the Moqui database and user:
                CREATE DATABASE moqui CHARACTER SET utf8;
                CREATE USER 'moqui'@'localhost' IDENTIFIED BY '@12345abC';
                GRANT ALL PRIVILEGES ON moqui.* TO 'moqui'@'localhost';
                FLUSH PRIVILEGES;
        Step 4: Update Moqui Configuration for Database
            Modified runtime/conf/MoquiDevConf.xml with database details:
             <default-property name="entity_ds_host" value="127.0.0.1"/>
             <default-property name="entity_ds_db_conf" value="mysql8"/>
             <default-property name="entity_ds_database" value="moqui"/>
             <default-property name="entity_ds_user" value="root"/>
             <default-property name="entity_ds_password" value="2304"/>
