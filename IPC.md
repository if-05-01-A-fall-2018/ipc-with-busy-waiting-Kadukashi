# Basics of Interprocess Communication

## 1 Race Condition:
  A race condition is an undesirable situation that arises when a device or system attempts to perform two or more operations simultaneously.

  Eine Race Condition (ein Wettrennen um den Zugriff auf Ressourcen) ist eine unerwünschte Situation, die entsteht, wenn ein Gerät oder System versucht, zwei oder mehr Operationen gleichzeitig auszuführen.

## 2 Disabling Interrupts
### **2.1**
In a multi-core machine, each CPU executes code simultaneously,
so whether the current CPU has disabled interrupts does not avoid other CPU from entering the same region.

### **2.2**
  It is unwise to give user processes the power to turn off interrupts, 
  because it could be that the user process disables iterupts accidentally.
 

## 3 Peterson's Solution
### **3.1**
1. Process 0 entered enter_region.
   Now it is blocking all other processes from joining.
   Process 0 is finishing it.
   Process 1 is waiting for 0 to finish.
   After process 0 leaves the region, process 1 is not blocked anymore and it is allowed to go into the critical area and to finish.

2. Both processes will get blocked in the while since both are interested and both are initialized.

### **3.2**
  Both will get blocked in the while since both are interested and both are initialized.
  The second scenario will fail.

### **3.3**
  The `loser` process is not allowed to go to the critical Area.

### **3.4**
