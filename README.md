#SQLiteUnityKit
==============

Framework to connect to SQLite database from Unity for iOS, Android, MAC and Windows

<b>***** please don't use this code for sell an asset *****</b>

##change log
###v 1.1 changes:
* Add android support (read below how to do)
* sqlite libs version for android (v3.3.17) It has been compiled with the android native development kit release 9 and the target arm is ARMv5TE (which should cover most android devices).
* change all DllImport from internal to private



###How to Use:

	SqliteDatabase sqlDB = new SqliteDatabase(“config.db”);
	string query = “INSERT INTO User(UserName) VALUES( ‘Santiago’)”;
	sqlDB.ExecuteNonQuery(query);


####IMPORTANT: 
the file *“config.db”* is necessary exist in the **“StreamingAssets”** folder.

If this folder does not exist create it in the root folder of your Unity project.
  
When running your project from Unity Editor on Mac, a folder in Application Support is created at: 
"/Users/YOUR_NAME/Library/Application Support/DefaultCompany/PROJECT_NAME"
you can find modified sqlite file there.
</br></br>


###to execute a query this libs have 2 simple methods:

	void ExecuteNonQuery(string query)  //for SQL query like UPDATE, DELETE....
	Dictionary ExecuteQuery(string query)  //for SQL query like SELECT ....
	
###parameter escaping:
Just pass a List<> as the second parameter of this methods and include them in your query, with "?" or "@param" as in regular SQLite.

##for Android compatibility:
</br>
Copy the file *"libsqlite3.so"* (sqlite libs for android) into the folder *"Assets/Plugins/Android"* **it's important copy that otherwise it will not be included to the final apk package.**

follow this simple steps and you can get full compatibility with android.


# credits
 * First version developed by Poya  @  http://gamesforsoul.com/
 * BLOB support by Jonathan Derrough @ http://jderrough.blogspot.com/
 * modify by Santiago Bustamante @ busta117@gmail.com
 * Android compatibility by Thomas Olsen @ olsen.thomas@gmail.com
 * Parameter escaping and iOS 64 bit compatibility by Scalia @ http://scalia.es

<br/>

####feedback?

* twitter: [@busta117](http://www.twitter.com/busta117)
* mail: <busta117@gmail.com>
* <http://www.santiagobustamante.info>
