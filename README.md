# SEJavaMini
Learn Github version controlling tool and use it for JAVA mini project.
Preparing to implement the code in git.
1 	 	/*Attendance Manager*/
 2 	 	/*
 3 	 	Made by
 4 	 	Ishwari Dawkhar 232012(ROll no)
 5 	 	Sanket Deshmane 232014(ROll no)
 6 	 	Pratik Jagtap 232029(ROll no)
 7 	 	Digvijay Desai 232012(ROll no)
 8 	 	*/
 9 	 	import java.util.Scanner;
 10 	 	
 11 	 	class User {
 12 	 	    protected String userName;
 13 	 	    protected String email;
 14 	 	    protected String password;
 15 	 	    Scanner sc=new Scanner(System.in);
 16 	 	
 17 	 	    User(){
 18 	 	        
 19 	 	        userName = email = password = " ";
 20 	 	    
 21 	 	    }
 22 	 	    
 23 	 	    public void AcceptDetails(){}
 24 	 	
 25 	 	}
 26 	 	
 27 	 	class Teacher extends User {
 28 	 	    
 29 	 	    String ID;
 30 	 	    
 31 	 	    public void AcceptDetails() {
 32 	 	        
 33 	 	    
 34 	 	        
 35 	 	        System.out.println("Enter ID: ");
 36 	 	        ID = sc.nextLine();
 37 	 	        
 38 	 	        System.out.println("Enter name:");
 39 	 	        userName = sc.nextLine();
 40 	 	        
 41 	 	        System.out.println("Enter password:");
 42 	 	        password = sc.nextLine();
 43 	 	        
 44 	 	        
 45 	 	    }
 46 	 	    
 47 	 	    public void displayData() {
 48 	 	        System.out.println(ID + "\t\t" + userName);
 49 	 	    }
 50 	 	    
 51 	 	    public int search(final String number, final String password) {
 52 	 	        if (ID.equals(number) && this.password.equals(password)) {
 53 	 	            return 1;
 54 	 	        } else
 55 	 	            return 0;
 56 	 	    }
 57 	 	    
 58 	 	    
 59 	 	}
 60 	 	
 61 	 	
 62 	 	class Student extends User {
 63 	 	    
 64 	 	    int rollNo;
 65 	 	    String dept;
 66 	 	    int attendance;
 67 	 	    
 68 	 	    Student(){
 69 	 	        
 70 	 	        rollNo = -1;
 71 	 	        dept = "";
 72 	 	        attendance = 0;
 73 	 	    
 74 	 	    }
 75 	 	    public int get_rollno() {
 76 	 	        
 77 	 	      return rollNo;
 78 	 	    
 79 	 	    }
 80 	 	
 81 	 	    
 82 	 	    public void AcceptDetails() {
 83 	 	        
 84 	 	        System.out.println("Enter name:");
 85 	 	        userName = sc.nextLine();
 86 	 	        
 87 	 	        System.out.println("Enter password:");
 88 	 	        password = sc.nextLine();
 89 	 	        
 90 	 	        System.out.println("Enter Department:");
 91 	 	        dept = sc.nextLine();
 92 	 	          
 93 	 	        System.out.println("Enter Roll number:");
 94 	 	        rollNo = sc.nextInt();
 95 	 	        sc.nextLine();
 96 	 	
 97 	 	    }
 98 	 	    
 99 	 	    public int search(final int number, final String password) {
 100 	 	        if (this.rollNo == number && this.password.equals(password)) {
 101 	 	            return 1;
 102 	 	        } else
 103 	 	            return 0;
 104 	 	    }
 105 	 	    public void markAttendance() {
 106 	 	        attendance++;
 107 	 	    }
 108 	 	    public void DisplayAttendance(){
 109 	 	        
 110 	 	        System.out.println(rollNo + "\t" + attendance + "\t\t\t" + userName);
 111 	 	    }
 112 	 	    
 113 	 	    public void displayDetails() {
 114 	 	
 115 	 	        System.out.println(rollNo + "\t\t" + dept + "\t\t\t" + attendance + "\t\t\t" + userName);
 116 	 	    
 117 	 	    }
 118 	 	    
 119 	 	    public void changePassword(final String Npassword) {
 120 	 	        password = Npassword;
 121 	 	    }
 122 	 	
 123 	 	}
 124 	 	
 125 	 	
 126 	 	public class Main {
 127 	 	    
 128 	 	    
 129 	 	    public static void main(String[] args) {
 130 	 	        
 131 	 	        Scanner sc = new Scanner(System.in);
 132 	 	        Student[] S = new Student[100];
 133 	 	        Teacher[] T = new Teacher[10];        
 134 	 	         
 135 	 	        int choice ,size = 0;
 136 	 	        String adminID = "ADMIN";
 137 	 	        String adminPassword = "ADMIN";
 138 	 	        String ID, password;
 139 	 	        do {
 140 	 	            
 141 	 	            System.out.println("\n1.Admin\n2.Teacher\n3.Student\n99.EXIT");
 142 	 	            System.out.print("\t\tEnter your choice: ");
 143 	 	            choice = sc.nextInt();
 144 	 	            
 145 	 	            
 146 	 	            switch(choice) {
 147 	 	            
 148 	 	            case 1:
 149 	 	                System.out.print("\nEnter User ID: ");
 150 	 	                ID = sc.next();
 151 	 	                
 152 	 	                System.out.print("\nEnter password: ");
 153 	 	                password = sc.next();
 154 	 	                
 155 	 	                if(ID.equals(adminID) && password.equals(adminPassword)) {
 156 	 	                    System.out.println("\t\tLOGIN Successful");
 157 	 	                    adminCase(S, T);
 158 	 	                    
 159 	 	                }else 
 160 	 	                    System.out.println("\t\tERROR : Incorrect credentials! ");
 161 	 	                break;
 162 	 	            case 2:
 163 	 	                               teacherCase(S, T);
 164 	 	                               break;
 165 	 	            case 3:
 166 	 	                studentCase(S);
 167 	 	                break;
 168 	 	            }
 169 	 	                
 170 	 	        }while(choice != 99);
 171 	 	
 172 	 	                
 173 	 	        sc.close();
 174 	 	    }
 175 	 	    static int sizeT = 0, sizeS = 0;
 176 	 	    public static void adminCase(Student S[], Teacher T[]) {
 177 	 	        
 178 	 	        Scanner sc = new Scanner(System.in);
 179 	 	        int choice;
 180 	 	        do {
 181 	 	            
 182 	 	            System.out.println("\n1.Create Students\n2.Display students attendance\n3.Add Teachers\n4.DIsplay Teachers\n99.EXIT");
 183 	 	            System.out.print("\t\tEnter your choice: ");
 184 	 	            choice = sc.nextInt();
 185 	 	            
 186 	 	            switch(choice) {
 187 	 	            
 188 	 	            case 1:
 189 	 	                System.out.println("Enter number of students to add(100 max): ");
 190 	 	                sizeS = sc.nextInt();
 191 	 	                if(sizeS > 100) {
 192 	 	                    System.out.println("Size limit exceeded");
 193 	 	                    System.out.println("Enter number of Students to add again(10 max): ");
 194 	 	                    sizeS = sc.nextInt();
 195 	 	                }
 196 	 	                for (int i = 0; i < sizeS; i++)
 197 	 	                    S[i] = new Student();
 198 	 	                
 199 	 	                for(int i = 0; i < sizeS; i++)
 200 	 	                    S[i].AcceptDetails();
 201 	 	                break;
 202 	 	            case 2:
 203 	 	                System.out.println("Roll No\tTotal Attendance\tStudent Name");
 204 	 	                for(int i = 0; i < sizeS; i++)
 205 	 	                    S[i].DisplayAttendance();
 206 	 	                break;
 207 	 	            case 3:
 208 	 	                System.out.println("Enter number of Teachers to add(10 max): ");
 209 	 	                sizeT = sc.nextInt();
 210 	 	                if(sizeT > 10) {
 211 	 	                    System.out.println("Size limit exceeded");
 212 	 	                    System.out.println("Enter number of Teachers to add again(10 max): ");
 213 	 	                    sizeT = sc.nextInt();
 214 	 	                }
 215 	 	                    
 216 	 	                for (int i = 0; i < sizeT; i++)
 217 	 	                    T[i] = new Teacher();
 218 	 	            
 219 	 	                for(int i = 0; i < sizeT; i++)
 220 	 	                    T[i].AcceptDetails();
 221 	 	                break;
 222 	 	            case 4:
 223 	 	                System.out.println("ID\t\tTeacher Name");
 224 	 	                for(int i = 0; i < sizeT; i++)
 225 	 	                    T[i].displayData();
 226 	 	                
 227 	 	            }
 228 	 	            
 229 	 	                
 230 	 	        }while(choice != 99);
 231 	 	    }
 232 	 	    
 233 	 	    public static void teacherCase(Student S[], Teacher T[]) {
 234 	 	         Scanner sc = new Scanner(System.in);
 235 	 	                String number, pass;
 236 	 	                int i;
 237 	 	                int x = 0;
 238 	 	                int p = 0;
 239 	 	                int k;
 240 	 	                int choice; 
 241 	 	                System.out.println("Enter ID: ");
 242 	 	                number = sc.next();
 243 	 	                System.out.println("Enter Password: ");
 244 	 	                pass = sc.next();
 245 	 	                
 246 	 	                for(i=0;i<sizeT;i++)
 247 	 	                {
 248 	 	                x=T[i].search(number, pass);
 249 	 	                  if(x==1)
 250 	 	                  {
 251 	 	                     p=i;
 252 	 	                    break;
 253 	 	                  }
 254 	 	                }
 255 	 	                if(x==1)
 256 	 	                {
 257 	 	                     System.out.println("\nLogin Successfull");
 258 	 	                     do {
 259 	 	            
 260 	 	            System.out.println("\n1-Displaydata\n2.Mark Attemdance \n3-Display Attendance\n99.EXIT");
 261 	 	            System.out.print("\t\tEnter your choice: ");
 262 	 	                choice = sc.nextInt();
 263 	 	            
 264 	 	            switch(choice) {
 265 	 	                       case 1 : System.out.println("ID\t\tTeacher Name");
 266 	 	                           T[p].displayData();
 267 	 	                                break;
 268 	 	            
 269 	 	            case 2: System.out.println("If student is present enter 1 else enter 0");
 270 	 	                               for(i=0;i<sizeS;i++)
 271 	 	                               {
 272 	 	                                 k= S[i].get_rollno();
 273 	 	                                 System.out.println("Roll No "+k+" is present/absent");
 274 	 	                                 int e=sc.nextInt();
 275 	 	                                 if(e==1)
 276 	 	                                 S[i].markAttendance();
 277 	 	                               }
 278 	 	                
 279 	 	                break;
 280 	 	            case 3: 
 281 	 	                                 System.out.println(" Displaying Attendace");
 282 	 	                                 System.out.println("Roll No\tTotal Attendance\tStudent Name");
 283 	 	                               for(i=0;i<sizeS;i++)
 284 	 	                               {
 285 	 	                                   S[i].DisplayAttendance();
 286 	 	                               }
 287 	 	                
 288 	 	                break;
 289 	 	                        default : System.out.println("\nWrong Choice");
 290 	 	            }
 291 	 	            
 292 	 	                
 293 	 	        }while(choice != 99);
 294 	 	                     
 295 	 	                     
 296 	 	                  }else      
 297 	 	                   System.out.println("Login unsuccessfull"); 
 298 	 	        
 299 	 	    }
 300 	 	    
 301 	 	     public static void studentCase(Student S[]) {
 302 	 	            Scanner sc = new Scanner(System.in);
 303 	 	            int op,i; int number ; String Npassword,p;
 304 	 	            int m=0; int n=0;
 305 	 	            System.out.println("Enter Roll number: ");
 306 	 	            number = sc.nextInt();
 307 	 	            System.out.println("Enter Password: ");
 308 	 	            p = sc.next();
 309 	 	            
 310 	 	            for( i=0; i<sizeS;i++)
 311 	 	            {
 312 	 	                m=S[i].search(number, p);
 313 	 	                if(m==1)
 314 	 	                {
 315 	 	                    n=i;
 316 	 	                    break;
 317 	 	                }
 318 	 	            }
 319 	 	            if(m==1)
 320 	 	            {
 321 	 	                System.out.println("\n login sucessful");
 322 	 	                do{
 323 	 	                System.out.println("\n1. View Student Information\n2. View Attendance\n3. Change password\n4. EXIT");
 324 	 	                System.out.println("\t\tEnter your choice: ");
 325 	 	                op=sc.nextInt();
 326 	 	                switch(op)
 327 	 	                {
 328 	 	                case 1:System.out.println("rollNo" + "\t\t" + "Department" + "\t\t" + "attendance" + "\t\t" + "Student Name");
 329 	 	                       S[n].displayDetails();
 330 	 	                       break;
 331 	 	                case 2:System.out.println("Roll No\tTotal Attendance\tName");
 332 	 	                        S[i].DisplayAttendance();
 333 	 	                        break;
 334 	 	                case 3:
 335 	 	                        System.out.println("enter New password");
 336 	 	                        Npassword = sc.next();
 337 	 	                        if(Npassword.equals(p))
 338 	 	                        {
 339 	 	                            System.out.println("Password cannot be same as the previous one");
 340 	 	                        } 
 341 	 	                        else
 342 	 	                        {
 343 	 	                            S[i].changePassword(Npassword);
 344 	 	                            System.out.println("Password changed succesfully");
 345 	 	                        }
 346 	 	                        break;
 347 	 	               default:System.out.println("Enter choice according to menu");
 348 	 	           }
 349 	 	            }while(op!=4);
 350 	 	            }else
 351 	 	            System.out.println("Login Unsucessfull");
 352 	 	        }
 353 	 	
 354 	 	}
 355 	 	

