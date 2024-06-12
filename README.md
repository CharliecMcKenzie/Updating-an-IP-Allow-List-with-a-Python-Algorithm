 <h1>Updating an IP Allow List with a Python Algorithm</h1>
 
 <h2>Project Overview</h2>
 At my organization, access to restricted content is controlled through an IP allow list specified in the "allow_list.txt" file. We also maintain a remove list to identify IP addresses that should no longer have access. To automate the update process, I developed a Python algorithm to modify the "allow_list.txt" file by removing IP addresses listed in the remove list.

 <h2>Program walk-through:</h2>
 
 <h3>Opening the Allow List File</h3>
 The first step of the algorithm involves opening the "allow_list.txt" file. I assigned the filename to a variable, import_file, and used a with statement to open the file in read mode:
<p align="center">
 <br />
<img src="https://i.imgur.com/w0aQ4nu.png" height="80%" width="80%" alt="IP allow list"/>
 <br />

 The with statement ensures the file is properly closed after its contents are read, thus managing resources efficiently.

<h3>Reading File Contents</h3> 
Next, I used the .read() method to convert the file's contents into a string:
<p align="center">
 <br />
<img src="https://i.imgur.com/BtnK6Cl.png" height="80%" width="80%" alt="IP allow list"/>
<br />

This step reads the entire file and stores the IP addresses as a single string in the variable ip_addresses.

<h3>Converting String to List</h3>
To facilitate the removal of individual IP addresses, I converted the string to a list using the .split() method:
<p align="center">
 <br />
<img src="https://i.imgur.com/QgVSvQM.png" height="80%" width="80%" alt="IP allow list"/>
<br />

This method splits the string into a list of IP addresses, making it easier to manipulate the data.

<h3>Iterating Through the Remove List</h3>
The core of the algorithm involves iterating through the IP addresses in the remove_list and removing any that are present in the ip_addresses list. A for loop is used for this purpose:
<p align="center">
 <br />
<img src="https://i.imgur.com/j35cOK9.png" height="80%" width="80%" alt="IP allow list"/>
<br />

This loop checks each element in remove_list and removes it from ip_addresses if it exists.

<h3>Updating the Allow List File</h3>
Finally, I updated the "allow_list.txt" file with the revised list of IP addresses. First, I converted the list back into a string using the .join() method:
<p align="center">
 <br />
<img src="https://i.imgur.com/nw6Zt67.png" height="80%" width="80%" alt="IP allow list"/>
<br />

Then, I wrote the updated string back to the file:
<p align="center">
 <br />
<img src="https://i.imgur.com/Bc8MD2c.png" height="80%" width="80%" alt="IP allow list"/>
<br />

This process ensures the allow list is updated to exclude IP addresses listed in the remove list.

<h3>Summary</h3>
The algorithm I created automates the removal of IP addresses from the "allow_list.txt" file based on a separate remove list. It involves reading the file, converting its contents to a list, iterating through the remove list to delete specified IP addresses, and finally writing the updated list back to the file. This ensures that access to restricted content is managed efficiently and accurately.
