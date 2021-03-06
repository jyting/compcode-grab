# Competition Code Grabber

Little utility to grab daily competition codes from TV streaming websites. Basically what it does is grab the streaming links from TV sites, uses ffmpeg to do image captures of them at short intervals, and detect when codeword screenshots pop up, and process them/extract the word from the image, and email it.

Currently only doing channel 7, as the encrypted stream links are directly available. Channel 9 requires both login and Flash, but will look into it at a later date.

Available functionality:
* Filter the collected images to only keep valid images (otherwise there'll be thousands a day)
* Identify the actual text in the relevant images
* Email the codeword for each day

Future (maybe) functionality:
* Automatically text the codeword each day (not sure if able to programmatically text to 19XX- numbers)

## Steps to run
1. Create 'imgs' directory in project root to hold temporary images (non-codeword image are all deleted every several seconds)
2. Make a copy of .env.example as .env, and populate the environment variables
    * EMAIL, EMAIL_PWD are your gmail and gmail password for the account to send *from*
    * NOTIFY_EMAILS is a comma-separated list of emails you want to email the codeword for the day to
3. Run the utils/montior_new_imgs.sh script 
4. Run utils/stream.sh to start capturing periodic screenshots from the channel 7 stream!
