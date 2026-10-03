from flask import Flask, render_template, request
from datetime import datetime  # Import time module

app = Flask(__name__)
# Here's a dict to saving items
history_list = []

@app.route('/', methods=['GET', 'POST'])
def index():
    result = ""
    expr = ""
    if request.method == "POST":
        expr = request.form.get("expression")
        try:
            result = eval(expr)
            # Gain time
            now_time = datetime.now().strftime("%Y-%m-%d %H:%M:%S")
            # Save to dict
            record = {
                "time": now_time,
                "expr": expr,
                "res": result
            }
            history_list.append(record)
        except ZeroDivisionError:
            result = "∞"
        except Exception:
            result = "你输东西，给我输好的啊！"

    return render_template("index.html", result=result, expr=expr, history=history_list)

if __name__ == '__main__':
    app.run(debug=True, port=5000)
