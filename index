<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>Flask Web Calculator</title>
    <style>
        .container{
            width:400px;
            margin:80px auto;
        }
        input{
            width:300px;
            height:40px;
            font-size:20px;
        }
        button{
            height:44px;
            font-size:18px;
        }
        .res{
            margin-top:20px;
            font-size:22px;
        }
        .history{
            margin-top:30px;
            text-align:left;
            border-top:1px solid #999;
            padding-top:20px;
        }
        .history-item{
            font-size:16px;
            margin:8px 0;
        }
        .time-text{
            color:#666;
            font-size:13px;
        }
    </style>
</head>
<body>
<div class="container">
    <h2>Here is a calculator, you can calculate something</h2>
    <!--Submit-->
    <form method="post">
        <input type="text" name="expression" value="{{expr}}" placeholder="For example: z">
        <button type="submit">=</button>
    </form>
    <div class="res">Result：{{result}}</div>

    <div class="history">
        <h3>Calculation History</h3>
        {% if history %}
            {% for item in history %}
                <div class="history-item">
                    <div>{{ item.expr }} = {{ item.res }}</div>
                    <div class="time-text">🕒 {{ item.time }}</div>
                </div>
            {% endfor %}
        {% else %}
            <div style="color:#666">No calculation records yet</div>
        {% endif %}
    </div>
</div>
</body>
</html>
