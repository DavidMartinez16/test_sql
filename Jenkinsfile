import groovy.sql.Sql

pipeline {
    agent {
        label 'Node_agent_1'
    }
        
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
                    def results = sql.rows("EXEC xp_cmdshell 'wmic OS get FreePhysicalMemory'")
                    println results
                    
                    sql.close()
                }
            }
        }
        stage('Virtual Memory') {
            steps {
                echo 'Connecting to El Colombiano'
                script {
                   
                    // Define a Map with the credentials for the DB
                    def dbConf = [URL: "jdbc:sqlserver://10.95.1.146", username:"usermonitoreo", 
                                password:"X1mma2012", driver:"com.microsoft.sqlserver.jdbc.SQLServerDriver"]
                    // Create the Connection with SQL Server
                    def sql = Sql.newInstance(dbConf.URL, dbConf.username, dbConf.password, dbConf.driver)
                    
                    //def results = sql.rows("select @@version")
                    def results = sql.rows("EXEC xp_cmdshell 'wmic OS get FreeVirtualMemory'")
                    println results
                    
                    sql.close()
                }
            }
        }
        stage('Cores') {
            steps {
                echo 'Connecting to El Colombiano'
                script {
                   
                    // Define a Map with the credentials for the DB
                    def dbConf = [URL: "jdbc:sqlserver://10.95.1.146", username:"usermonitoreo", 
                                password:"X1mma2012", driver:"com.microsoft.sqlserver.jdbc.SQLServerDriver"]
                    // Create the Connection with SQL Server
                    def sql = Sql.newInstance(dbConf.URL, dbConf.username, dbConf.password, dbConf.driver)
                    
                    //def results = sql.rows("select @@version")
                    def results = sql.rows("EXEC xp_cmdshell 'wmic cpu get numberofcores'")
                    println results
                    
                    sql.close()
                }
            }
        }
        stage('Filesystem') {
            steps {
                echo 'Connecting to El Colombiano'
                script {
                   
                    // Define a Map with the credentials for the DB
                    def dbConf = [URL: "jdbc:sqlserver://10.95.1.146", username:"usermonitoreo", 
                                password:"X1mma2012", driver:"com.microsoft.sqlserver.jdbc.SQLServerDriver"]
                    // Create the Connection with SQL Server
                    def sql = Sql.newInstance(dbConf.URL, dbConf.username, dbConf.password, dbConf.driver)
                    
                    //def results = sql.rows("select @@version")
                    def results = sql.rows("EXEC xp_cmdshell 'fsutil volume diskFree C:'")
                    println results
                    
                    sql.close()
                }
            }
        }
        stage('Winver') {
            steps {
                echo 'Connecting to El Colombiano'
                script {
                   
                    // Define a Map with the credentials for the DB
                    def dbConf = [URL: "jdbc:sqlserver://10.95.1.146", username:"usermonitoreo", 
                                password:"X1mma2012", driver:"com.microsoft.sqlserver.jdbc.SQLServerDriver"]
                    // Create the Connection with SQL Server
                    def sql = Sql.newInstance(dbConf.URL, dbConf.username, dbConf.password, dbConf.driver)
                    
                    //def results = sql.rows("select @@version")
                    def results = sql.rows("EXEC xp_cmdshell 'winver'")
                    println results
                    
                    sql.close()
                }
            }
        }
    }
}
