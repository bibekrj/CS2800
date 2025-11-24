## Your workflow from your IDE/Terminal to AWS may look like

Local Project ----> Zip ----> AWS  ---> UnZip ----> /var/www/html 
Local Project ----> GitHub ----> Clone to AWS -----> /var/www/html

### To navigate around terminal
1. Check where you're at/print your current working directory = **pwd**
2. Check the contents of the current directory/List directory = **ls** or **ls -l** or **ls -al**
3. Navigate to another folder/Change directory = **cd** /<foldername>


## Instruction for copying your website on AWS
### ------ Local Machine ------
1. ***zip*** your project folder using any tool
2. ***SCP*** zipped file/folder to server using the pem and IP
```
	scp -i labsuser.pem demo.zip ubuntu@xxx.xxx.xxx.xxx: (replace xxx with your PUBLIC IP)
```
### ------ OR ------
1. Set up GitHub keys on AWS using ssh-keygen
2. ***git clone*** your final repository to AWS 

### ------ ON SERVER ------
3. IF you used SCP &  ***unzip*** is not installed, 
```
	sudo apt install unzip
```
4. ``` unzip <filename>.zip ``` \<filename> replaced with the actual file name
5. copy your files to ```/var/www/html```
	``` sudo cp -r folder/* /var/www/html/ ```
6. Check your website from a browser tab with your Public IP address.

## Folder structure inside ```/var/www/html/``` MUST imitate the following structure
```
- index.html
- pages/
	- page1.html
	- page2.html
	- page3...cont.
- style.css
- script.js
- images/
	- image1.jpg
	- image2.jpg
	- image3....cont.
```