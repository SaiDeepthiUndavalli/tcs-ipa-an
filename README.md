class News:
    def __init__(self,no,name,year,price):
        self.no=no
        self.name=name
        self.year=year
        self.price=price
        
class Agency:
    def __init__(self,db):
        db={}
    def search(self,yg):
        b=[]
        flag=0
        for i,j in self.db.items():
            if j.year==yg:
                flag=1
                b.append(j)
        if flag==1:
            return b 
        else:
            return None
            
    def cal(self,ng):
        total=0
        for i,j in self.db.items():
            if j.name==ng:
                total=total+j.price
        return total    
        
n=int(input())
db={}
for i in range(n):
    no=int(input())
    name=input()
    year=int(input())
    price=int(input())
    db[no]=News(name,year,price)
ob=Agency(db)
yg=int(input())
s=ob.search(yg)
if s!=None:
    for i in s:
        print(i.no)
        print(i.name)
        print(i.year)
        print(i.price)
else:
    print("No newspaper found")
    
ng=input()
v=ob.cal(ng)

print('Total price',v)
