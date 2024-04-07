# Bulky-sms-
from twilio.rest import Client

def send_sms(account_sid, auth_token, from_number, to_number, message_body):
    """
    Sends an SMS using Twilio API.

    :param account_sid: Twilio Account SID
    :param auth_token: Twilio Auth Token
    :param from_number: Twilio phone number sending the message
    :param to_number: Recipient's phone number
    :param message_body: Body of the SMS message
    """
    try:
        # Initialize Twilio client
        client = Client(account_sid, auth_token)

        # Send the message
        message = client.messages.create(
            body=message_body,
            from_=from_number,
            to=to_number
        )

        print("Message sent successfully to", to_number)
    except Exception as e:
        print("Error:", e)

def main():
    # Twilio credentials
    account_sid = 'AC9a9d7965346804620c809b92745b0f35'
    auth_token = '170a897461baef54da43532aa9dcafc6'

    # Twilio phone number
    from_number = '+12057297262'

    # Recipient's phone number (your contact number)
    to_number = '7987882931'

    # Message content
    message_body = 'CG BSC Nursing , PPHT प्रवेश परीक्षा के लिए निःशुल्क डेमो क्लास  10 अप्रैल तक
💥 फिजिक्स, बायलॉजी,केमिस्ट्री ,
💥11वी व 12 वी 
💥क्लास का समय 12.30 से 5 बजे तक
💥 2 महीने का क्रैश कोर्स.'

    # Send the SMS
    send_sms(account_sid, auth_token, from_number, to_number, message_body)

if __कैरियर कोचिंग एकेडमी चारामा__ == "__main__":
    main()
