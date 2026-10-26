ה: docker build -t greeter:v1 lessons/02-docker-basics/homework/greeter/
הרצה: docker run -d --name greeter -p 9000:8000 greeter:v1.
שינוי הברכה: מוסיפים -e GREETING=Shalom לפקודת ה-run.
התשובה של /hello/Rivka: {"message": "Shalom, Rivka!"}
Cache: אחרי שינוי ב-app.py, השלבים FROM, WORKDIR, COPY requirements.txt ו-RUN pip install יסומנו CACHED. COPY app.py ומה שבא אחריו (EXPOSE, CMD) ירוצו מחדש. Docker בונה מחדש שלב שהקלט שלו השתנה ואת כל השלבים שאחריו. requirements.txt לא השתנה, ולכן התקנת התלויות נשארת ב-cache.
