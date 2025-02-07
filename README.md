# Reddit Miner

Automated data mining off of Reddit's front page and storage in database for data analysis and visualization. Local application built on Node.js.

## Getting Started

Download the .zip file and extract all files into directory of your choice. Open folder in preferred text editor.

### Prerequisites

1. Text Editor (Visual Studio Code)
2. MongoDB Atlas Account OR local MongoDB instance

### Installing

1. Download the `.zip` and extract in a desired working directory
2. Open the extracted folder in the text editor of your choice
3. Create a new file within the `Reddit-Miner-master` folder called `keys.js`
4. Within `keys.js` enter the following code:

```
var atlasURL = {
    url: < your mongoDB Atlas URL with credentials >
    email: < your sender email address >
    password: < your sender email password >
    recieveEmail: < your reciever email address >
}

module.exports = atlasURL;
```
**url**: replace with the URL to your MongoDB Atlas database. This URL can be found by selecting your desired cluster then clicking 'connect' -> 'Connect your application'

**email**: this will be the host email address. If you want to have email notifications when your program runs into errors, this will be the email sender address.

**password**: the appropriate password for the sender email address.

**recieveEmail**: the recieving email address. This can be your main email, or any email that you recieve notifications from so you can keep tabs on errors your program might run into.

**Save** the `keys.js` file

5. Open command line, navigate to the extracted `Reddit-Miner-master` working directory, and type the following:

```
node app.js
```
You should see a "server spinning up" message followed by a date and time.
You will then see "1 document inserted" for each post object that is written to the database.

Example Output:

```
==================================
Server: spinning up on port 27017
Time: 2019:12:07:21:43
----------------------------------
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
1 document inserted
```
There will always be 25 documents inserted for each request made.

## Current Issues

Requests made to some subreddits, specifically r/NintendoSwitch and r/news, return an error and can sometimes end the program.
I haven't figured out why this is, but if you run into this error, the console will log an axios request error.
I have some suspicion that these subreddits have a 'no bot' policy, so any requests made will not be fulfilled, but I haven't proven this yet.

## Built With

* [Node.js](http://www.nodejs.org/) - Javascript runtime
* [Axios](https://github.com/axios/axios) - Promise-based HTTP client
* [MongoDB](https://www.mongodb.com/) - Document-based distributed database

## Authors

* **Jamison Cozart** - *All* - (https://github.com/jamisoncozart)
