iimport json

class User:
    def __init__(self, username, password, email):
        self.username = username
        self.password = password
        self.email = email

class UserRepository:
    def __init__(self):
        self.users = []
        self.isLoggedIn = False
        self.currentUser = {}

        #load Users from .json file
        self.loadUser()
    def loadUser(self):
        pass   


    def register(self, user: User):
        self.users.append(user)
        self.savetoFile()
        print('Kullanici Olusturuldu.')
    def login(self):
        pass
    def savetoFile(self):
        list = []
        for user in self.users:
            list.append(json.dumps(user.__dict__))
        with open('users.json','w') as file:
            json.dump(list, file)
repository = UserRepository()
while True:
    print("Menü".center(50,'*'))
    secim = input('1- Register\n2- Login\n3- Logout\n4- identity\n5- Exit\nSeciminiz: ')              
    if secim == '5':
        break
    else:
        if secim == '1':
            username = input('username: ')
            password = input('password: ')
            email = input('email: ')

            user = User(username=username, password = password, email = email)
            repository.register(user)
            print(repository.users)
        elif secim == '2':
            pass #Login
        elif secim == '3':
            pass #Logout
        elif secim == '4':
            pass #display username
        else:
            print('Yanlis secim')    





