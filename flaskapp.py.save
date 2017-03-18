from flask import Flask, send_from_directory, request, render_template
import json
import os
import facebook
from random import shuffle
#from flask_mail import Message, Mail

#mail = Mail()

##access_token_obt = get_app_access_token(339214274055,"dff62227ae01cf4fe670dbc396b6c572")
#print access_token_obt

#theToken = os.environ["APP_ID"]
#print theToken
# TODO: Using environment variable

app = Flask(__name__)
app.config['DEBUG'] = True

# Test app sec key
app.secret_key = 'U\xcbz\x0e\xff-\x95\x8a;z\xb3&\xa8\x11\x08\xb6r\x7f#\xba#\xde~\xe0\nO\x7f0\x11\xddv\x05'

#app.config["MAIL_SERVER"] = "smtp.gmail.com"
#app.config["MAIL_PORT"] = 465
#app.config["MAIL_USE_SSL"] = True
#app.config["MAIL_USERNAME"] = 'nisbglimpse@gmail.com'
#app.config["MAIL_PASSWORD"] = 'nisb@nie'
#mail.init_app(app)

@app.route('/<path:resource>')
def serveStaticResource(resource):
    return send_from_directory('static/', resource)

@app.route('/')
def hello_world():
    graph = facebook.GraphAPI(access_token="1327383467301154|YDfQ94wTelbffydG5XrnanHnqu0", version='2.2')
    events = graph.request("/ankurafest/events", {
		"since": 0,
		"fields": "id, name, start_time, ticket_uri, place, description, cover",
	})
    image=[]
    #caption=[]
    bheek = graph.request("/496185003899064/photos",    {
        "since": 0,
        "fields": "name, images",
    })
    bheek=bheek["data"]
    shuffle(bheek)
    #caption.append(bheek[0]["name"])
    image.append(bheek[0]["images"][0]["source"])
    #caption.append(bheek[2]["name"])
    image.append(bheek[2]["images"][0]["source"])
    # bheek=bheek["data"]
    # image.append(bheek)
    bheek = graph.request("/496237300560501/photos",    {
        "since": 0,
        "fields": "name, images",
    })
    bheek=bheek["data"]
    shuffle(bheek)
    #caption.append(bheek[0]["name"])
    image.append(bheek[0]["images"][0]["source"])
    #caption.append(bheek[2]["name"])
    image.append(bheek[2]["images"][0]["source"])
    #bheek=bheek["data"]
    # image.append(bheek)
    bheek = graph.request("/496269680557263/photos",    {
        "since": 0,
        "fields": "name, images",
    })
    bheek=bheek["data"]
    shuffle(bheek)
    #caption.append(bheek[0]["name"])
    image.append(bheek[0]["images"][0]["source"])
    #caption.append(bheek[2]["name"])
    image.append(bheek[2]["images"][0]["source"])
    # bheek=bheek["data"]
    # image.append(bheek)
    # shuffle(image)
    # print(image)
    return render_template('index.html', event=events["data"], image=image)


'''
    There is this thing called multilined comments
    Its not that bad really
'''
#@app.route('/contact', methods=['GET', 'POST'])
#def contact():
#  name = request.form['name']
#  email = request.form['email']
#  sub = request.form['subject']
#  message = request.form['message']
#  msg = Message(sub, sender=email, recipients=['your_email@example.com'])
#  msg.body = """
#   From: %s <%s>
#     %s
#   """ % (name, email, message)
#  mail.send(msg)
#  return hello_world()

if __name__ == '__main__':
    app.run(debug=True)
