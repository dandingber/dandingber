# קוד אפליקציה משפחתית

class FamilyApp:
    def __init__(self):
        self.users = {}  # מילון לאחסון משתמשים ונקודות

    def add_user(self, username):
        if username not in self.users:
            self.users[username] = 0
            print(f"משתמש {username} נרשם בהצלחה!")

    def add_points(self, username, points):
        if username in self.users:
            self.users[username] += points
            print(f"נקודות עבור {username}: {self.users[username]}")
        else:
            print(f"משתמש {username} לא נמצא במערכת.")

    def redeem_points(self, username, secret_code):
        if username in self.users:
            if secret_code == "1234":  # קוד סודי
                print(f"מזל טוב, {username}! קיבלת 100 ש"ח לאמתיים!")
                self.users[username] -= 100
            else:
                print("קוד סודי שגוי.")
        else:
            print(f"משתמש {username} לא נמצא במערכת.")


# יצירת אובייקט מסוג FamilyApp
app = FamilyApp()

# הוספת משתמשים
app.add_user("אבא")
app.add_user("אמא")
app.add_user("ילד1")
app.add_user("ילד2")

# הוספת נקודות
app.add_points("אבא", 50)
app.add_points("ילד1", 30)
app.add_points("ילד2", 20)

# פיצול נקודות על פי קוד סודי
app.redeem_points("ילד1", "1234")
