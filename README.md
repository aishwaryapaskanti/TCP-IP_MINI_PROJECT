TCP BASED CHATING APPLICATION

Objective : Here the objective is to implement chating application to allow two persons for chating over a network i.e.., CLIENT1 and CLIENT2 , withhelp of SOCKET programming by using TCP protocols.

Task : Here client1 and client2 can not communicate directly, So we need server to handle client1 and client2. 
There are three versions can be posible i.e , simplex , half duplex and full duplex.

Consider FULL DUPLEX , Client1 will send message to server and that
server will send received message to client2 and vice versa.

Approach:Server should accept two clients connection with help of two
accept() calls i.e.., from client1 and client2
<img width="666" height="311" alt="image" src="https://github.com/user-attachments/assets/a176cf85-b195-4f6c-ac41-39c5e75db928" />

After connection estlabished , create child server. So , now we have two server processes i.e parentServer and childServer. Both are having connection with client1 and client2

<img width="628" height="265" alt="image" src="https://github.com/user-attachments/assets/60236181-ecf6-4757-a8e5-67b6e0cd3473" />

Now our task is to make full duplex, So , we need to create child
process to clients , after connect() call in clients.

<img width="688" height="437" alt="image" src="https://github.com/user-attachments/assets/6e398322-4e82-47e9-94a3-1b21ab358f77" />

Now to make full duplex, manage your if and else blocks in clients
and server as follows.
 client1_child always send MSG to server_child

 server_child always first recv MSG from client1_child and send to client2_parent.

 client2_parent always recv MSG from server_child

 client2_child always send MSG to serever_parent.

 server_parent always first recv MSG from client2_child and send to client1_parent.

 client1_parent always recv MSG from server_parent 

<img width="611" height="446" alt="image" src="https://github.com/user-attachments/assets/e4a00c50-2a48-426b-b19a-8aa43a917a24" />


