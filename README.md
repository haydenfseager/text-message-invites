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

Some of the challenges you faced and features you hope to implement in the future.

## How to Install and Run the Project


## How to Use the Project

## Challenges



## Credits


Wrap Up



What was your motivation?
Why did you build this project?
What problem does it solve?
What did you learn?
What makes your project stand out?
If your project has a lot of features, consider adding a "Features" section and listing them here.
