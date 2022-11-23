import groovy.sql.Sql

pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('CPU') {
            steps {
                echo 'Connecting to El Colombiano'
                script {
                    
                    // Define a Map with the credentials for the DB
                    def dbConf = [URL: "jdbc:sqlserver://10.95.1.146", username:"usermonitoreo", 
                                password:"X1mma2012", driver:"com.microsoft.sqlserver.jdbc.SQLServerDriver"]
                    // Create the Connection with SQL Server
                    def sql = Sql.newInstance(dbConf.URL, dbConf.username, dbConf.password, dbConf.driver)
                    
                    //def results = sql.rows("select @@version")
                    def results = sql.rows("EXEC xp_cmdshell 'wmic cpu get loadpercentage'")
                    println results
                    
                    sql.close()
                }
            }
        }
        stage('Memory') {
            steps {
                echo 'Connecting to El Colombiano'
                script {
                   
                    // Define a Map with the credentials for the DB
                    def dbConf = [URL: "jdbc:sqlserver://10.95.1.146", username:"usermonitoreo", 
                                password:"X1mma2012", driver:"com.microsoft.sqlserver.jdbc.SQLServerDriver"]
                    // Create the Connection with SQL Server
                    def sql = Sql.newInstance(dbConf.URL, dbConf.username, dbConf.password, dbConf.driver)
                    
                    //def results = sql.rows("select @@version")
                    def results = sql.rows("wmic OS get FreePhysicalMemory")
                    println results
                    
                    sql.close()
                }
            }
        }
    }
}
