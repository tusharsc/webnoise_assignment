# User Login Steps

### Installation Setps
For further reference, please consider the following sections:

#### Pre-Requisites on Local Machine
* Java 1.8
* Maven
* Mysql running on port 3306


#### Installation

* Once Installation is done follow following steps:
    * Set the properties into the application.properties as:
        * spring.datasource.username=(set your Mysql UserName)
        * spring.datasource.password=(set your Mysql password)
    * Optionally if the database name `test` or the port `3306` conflict with the existing configuration you can always change them by hand in `application.properties`

#### Steps to Run
* Run you project with mvn spring-boot:run and launch from browser with [http://localhost:8181/](http://localhost:8181/)

#### Documentation
* Once the app comes up you will find the documentation at http://localhost:8181/swagger-ui.html

#### Problem statement

* The app when it comes up will have 2 users created in the system -
  * `user1@gmail.com` with password `user1ABC`
  * `user2@gmail.com` with password `user2ABC`

* user1@gmail.com cant login but user2@gmail.com can

* You can use the `try it out` feature on the swagger page with for the `/login` API to simulate this.Alternately you can use any choice of REST client for the same.

* The output expected out of this is as follows
  * Debug why the login for user1@gmail.com fails.
  * Once the bug is discovered fix it and submit the assignment via git
  
##### Problem Report

as Problem statement provides 
* The app when it comes up will have 2 users created in the system -
  * `user1@gmail.com` with password `user1ABC`
  * `user2@gmail.com` with password `user2ABC`
  
  * user1@gmail.com cant login but user2@gmail.com can
* Similarly I try it out feature on the swagger page with for the `/login` API to simulate this.
 then i fixed this problem checking database, becoz in database there is duplicate LoginId in user table, thats why it gets fails to login with user1. 
 
 *In this scenario there is db folder , in that using liquibase library values are inserted in table user while database get created.
 * that values 1 st row is repeated,that i remove from changelog.xml file
 * after that i again run the application and debug and execute the login api with user1 , it get successful.
 
