from flask import Flask, render_template
from flask_sqlalchemy import SQLAlchemy

app = Flask(__name__)

app.config['SQLALCHEMY_TRACK_MODIFICATIONS'] = False
app.config['SQLALCHEMY_DATABASE_URI'] = 'mysql+mysqlconnector://root:''@127.0.0.1:3306/flask'
db = SQLAlchemy(app)


class DesSubArea(db.Model):
    id_des = db.Column(db.Integer, primary_key=True)
    des = db.Column(db.String(244), nullable=False)


db.create_all()


@app.route("/", methods=["GET"])
def main():
    return render_template("index.html")


@app.route("/sh", methods=["GET"])
def sh():

    return render_template("index.html", sub=DesSubArea.query.all())


if __name__ == "__main__":
    app.run()
