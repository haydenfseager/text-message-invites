# 🎉 Party Invitations Via Text Message
This is a Python project that helped me **invite a list of people** to my mom's 50th birthday party using [Twilio](https://www.twilio.com/messaging/sms)

## ✔️ Project Components
* [Python](https://www.python.org/doc/essays/blurb/)
* [Google Colab](https://research.google.com/colaboratory/faq.html#:~:text=Colaboratory%2C%20or%20%E2%80%9CColab%E2%80%9D%20for,learning%2C%20data%20analysis%20and%20education.)
* [Twilio](https://www.twilio.com/blog/what-does-twilio-do)
* [Microsoft Excel](https://www.microsoft.com/en-us/microsoft-365/excel)

## 📜 Project Description:
The **motivation** behind this project is that I was tasked with inviting about 75 people to my mom's surprise 50th birthday party. At first thought, I could just add all phone numbers into my phone and text them the invitations individually, but what happens if there's a change to the party's date, or if the entire group needs to be notified at once? This realization made me take to good ole python.

The basic **function** of this project is to mass text a list of phone numbers. In my case, I wanted to send a picture of the invitation and an RSVP message along with it. The program does this by referencing a the column of a CSV file to extract the phone numbers and place them into a python list. Then, using the **Twilio API**, it simply loops through the list of numbers, sending them each the picture and the message.

For this **implementation**, I used **Python** in **Google Colab**. Python was chosen for its ease of interfacing with various high-level applications, and Google Colab was chosen because you don't have to download, install, or run anything to use it. Additionally, I used **Excel** to create the **CSV file** for the phone numbers on the fly. Lastly, I needed a way to text phone numbers. I'm sure there's a way to do this with my personal phone number but I was trying my best not to interface with my phone. A quick google will show you that there are a [few text messaging APIs](https://rapidapi.com/blog/sms-apis-send-texts/). I can't remember the reason I chose Twilio, but every API should be similar. From there, it was pretty much straight foward: Research the Twilio-specific libraries to connecct everything together.

## 💻 How to Install and Run the Project
First, you need to make a **Twilio account**. You *can* make a free account; however, to send any message to a phone number using the free acount, you must pre-register that phone number into the Twilio system. You can see how this defeats the purpose if the number of phone numbers becomes very large. I simply just paid the $20 to bypass this.

I'm pretty new to **Google Colab**, but one thing I do know is that you can run your code in **individual blocks**. I've created a block of code for each part of the process.
1. Install the Twilio libraries
2. Test the CSV file import
3. Send the text messages to everyone

Start by running the **first block of code**, which should install the Twilio library. Then, you will need to make a series of edits.

`df = pd.read_csv('Name of your CSV file of phone numbers')` Change the inner quotes to the path of your CSV file. In Google Colab, you must either upload the file to the current Colab session, or upload it permanantly to your Google Drive. 

`phone_number_list  = df['Column Name'].to_string(index=False).split()` Change the inner quotes to the column name of your CSV file. 

`phone_number_list[i] = '+1' + phone_number_list[i]` Either remove this line because your CSV contains the phone number country codes, or change the '+1' to your country's phone code (granted all the numbers are from the same country).

**🧪 Run this block of code to ensure it reads your CSV file correctly.**

`account_sid = 'Found on your Twilio Account'` Copy and paste your SID from your Twilio account.

`auth_token = 'Found on your Twilio Account'` Copy and paste your Auth Token from your Twilio account. There is also a test SID and Auth Token if you need to test something before using it.

`twilio_phone_num = 'Found on your Twilio Account'` Copy and paste your new Twilio phone from your Twilio account. Once you are testing, you can verify this is the number from which you are receiving messages.

`my_phone_num = 'Insert Phone number Here'` Change the inner quotes to your phone number with the country code. This will act as your testing phone number.

`body= "Reminder to RSVP to Hayden!",` This is the message that will be texted to all the numbers. Change the inner quotes to whatever you please

`media_url='This must be a URL',` Change the inner quotes to a media URL if you wish to add a picture to your text message. If not, remove this line. Note: this must be a URL and not a JPG. The way I got around this was to upload my image to [Imgur](https://imgur.com/). Make sure you copy the image URL and not the webpage URL. It should end in .jpg

## How to Use the Project
Now that everything is set up, you can mass text your list of phone numbers whatever you want. Simply **run the third block of code**!
## Challenges
* Sometimes my friends and family would text me after I had already sent out the invites with a new number to add to the list. Since the program is set up to mass text everyone, it becomes a bit annoying to the people who have already RSVP'd to get another text message about the party every time I needed to 'add someone to the list'. This happened about 6 or 7 times. I would edit the code each time to select the individual numbers which was very inefficient and annoying. In the future, I would definitely create a UI to select who to text and what.
* Figuring out a way to make a local image have a URL link. I used Imgur to do this, but I'm sure this isn't the only way
* This program lacks a way to receive text messages back. I'm sure this is pretty straight foward to set up, I just didn't think it was necessary for the time.
