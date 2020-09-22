# Using BHR

## Blocking in BHR

1. Navigate to your BHR instance and click "Add Block" in the top menu bar
![BHR Block 1](img/bhr_block_1.png)
1. Input CIDR or IP address of host or subnet you wish to block, along with a description, and duration for the block, and click "Block."
![BHR Block 2](img/bhr_block_2.png)
1. Verify that the host has been blocked.
![BHR Block 3](img/bhr_block_3.png)


## Whitelisting in BHR

1. Navigate to https://your.bhr.instance.com/admin, and click "Whitelist entrys" under the "BHR" section
![BHR Whitelist 1](img/bhr_whitelist_1.png)
1. Click the "ADD WHITELIST ENTRY" button at the top right of the application
![BHR Whitelist 2](img/bhr_whitelist_2.png)
1. Insert IP address or subnet, select your username, add a description, and click "SAVE."
![BHR Whitelist 3](img/bhr_whitelist_3.png)
1. Verify that whitelist entry saved successfully.
![BHR Whitelist 4](img/bhr_whitelist_4.png)


## Querying Blocks in BHR

1. Navigate to your BHR instance, and click "Query" in the top menu bar.
![BHR Query 1](img/bhr_query_1.png)
1. Type IP address or subnet in text box and click "Query"
![BHR Query 2](img/bhr_query_2.png)
1. Results should be returned if there is currently a block in place, along with the time the host was blocked, and the time it will be removed from BHR
![BHR Query 3](img/bhr_query_3.png)


## Adding Users to BHR

1. Navigate to https://your.bhr.instance.com/admin, and click the "Add" link next to "Users" under "Authentication and Authorization"
![BHR User 1](img/bhr_user_1.png)
1. Set username and password, and click "Save and Continue Editing"
![BHR User 2](img/bhr_user_2.png)
1. Scroll down, and set Permissions. You can set these manually via the Available groups, or via the Staff status checkbox if you wish for the user to have admin access.
![BHR User 3](img/bhr_user_3.png)
1. Click "Save" to save the account
![BHR User 4](img/bhr_user_4.png)