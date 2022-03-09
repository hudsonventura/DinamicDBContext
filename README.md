# DinamicDBContext 
DinamicDBContext class to provide a easy access to a DB, using SQL string query or statement, when you can't use a ORM. See documentation how to use.


I disclame for you that DinamicDBContext must be used in a simple project, or project that you can't use a ORM, either by the complexity, or just a simple things.

If you want to talk to me, for any purpose, send me an email. hudsonventura@outlook.com

<br>

### The using...

using HudsonVentura;<br>
<br>
<br>

### How to create a connection to one database
```
var stringConnection = $"User Id=DBUSER;Password=DBPASS;Data Source=DBHOST:DBPORT/DNNAME";
var accessDB = new DinamicDBContext(new OracleConnection(stringConnection));
```

### How to make a simple SELECT query with just a entry<br>
```
var data = accessDB<MyClassToBind>queryOne($" SELECT * FROM wfprocess WHERE p.fgstatus in (1, 4) AND coupaid = '{id}'"
```

### How to make a simple SELECT query with many entries<br>
```
var data = accessDB<MyClassToBind>query($" SELECT * FROM wfprocess WHERE p.fgstatus in (1, 4) AND rownum <= 10"
```

### To prepare and query a statement<br>
```
In construction
```

### To execute a non query statement<br>
```
var data = accessDB<MyClassToBind>execute($"UPDATE wfprocess set test = 'ok' WHERE coupaid = '{id}'"
```