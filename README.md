# Configuration
## Aplication
### What it does:
• Checks the existence of the local version in the client's folder;
 
• If the file version does not exist, it assumes the version is "1.0" and creates a version file;
 
• Check .xml file on the update server;
 
• Download updates for all versions greater than the current version of the client (updates everything in .zip file format only);
 
• Extract the .zip files;
 
• Deletes .zip files after extraction;
 
• Archive the updated version in the client's folder;
 
• And finally unlocks the "Start Game" button.

### How to edit:
 
• Open the .sln file in the "VS Project" folder with Visual Studio:
 
Search for:

`string Server = "http://127.0.0.1/Updates/";`

• Change http://127.0.0.1/Updates/ to whatever URL you will be hosting your updates.
![image](https://user-images.githubusercontent.com/74227915/152198277-15177643-813f-458f-b661-51f31e72eb9c.png)

Now let's search for:
`Process.Start("PROCESS_NAME.exe", "\\PROCESS_NAME");`

• Modify the PROCESS_NAME.exe by the name of your exe.
 
• \\PROCESS_NAME and the folder that is your PROCESS_NAME.exe and will be your Launcher. (change without removing the "\\")
![image](https://user-images.githubusercontent.com/74227915/152198991-5210bd69-f39f-4244-898a-a147fbd5b68a.png)

In Visual Studio, select the WebBrowser control (In this case, name it "patchNotes") and change the url from `http://127.0.0.1/` to the path of the `index.html` file, in the host folder:
`Example : https://myweb.com/news` and it will render in app
![image](https://user-images.githubusercontent.com/74227915/152199363-36a3c2cf-b0d0-4c50-b707-9a0aa692c375.png)

NOTE: This is optional, it's just a template in .html. You can remove it and edit it however you want.
• Now just throw the .exe, .dll and the version file from the folder "Launcher\VS Project\Launcher v2\bin\Debug or Release" to your Client folder:

## Website

• On the site's host, after pasting the Updates folder, we edit the Updates.xml file, for each update we add an `<update> and close it with </update>` as in the example of the file. We put the update file in .zip in that same folder, editing the version and name in the file:

• In the file version.txt we put the version of the new update:
 
• A tip for the update .zip is to put in folders the path on the client you want to update. Example: data/things/854 in this folder we will place the files that will be replaced, in the example it was Tibia.spr and .dat. Then we compress it and leave it in the Updates folder, without forgetting to put the name in the Updates.xml file.

When you open the file it will update, release the "Start Game" button, and when you click it will close the Launcher and open the Client.
