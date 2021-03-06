# Azure Data Lake Store FAQ

### Q: I am an Owner/Contributor on an ADLS Account, Why don'I t have access to data in the ADLS Account.

This is *by design* Owner/Contributor is about managing the account not data access

Access to data is controlled solely through filesystem ACLs. 

NOTE: For ADLS Public Preview, there is a single ACL on the root folder of an ADLS account.

### Q: I am an Owner/Contributor on an ADLS Account, why can't I modify ACLs on the root folder.

For ADLS Public Preview, the only user who can change the ACL on the root folder is the Owner who created the ADLS account.

By ADLS General Availability, all the users listed as Owners for the ADLS account will be able to set the ACL on the root folder.

### Q: Can I set an ACL on a subfolder or file?

For ADLS Public Preview, there is a single ACL on the root folder of an ADLS account.

By  ADLS General Availability , ACLs will be available on any folder and on any file.

### Q: I just added/deleted files to an ADL Store but the total storage size for the account does not reflect the change.

When you see the size of an files, the size is up-to-date.

However anytime you see files sizes that are aggregated - for example in the case of the total data stored for the
entire account - those numbers are calculated in a background processes that runs every 24 hours. So those numbers 
can be out-of-date for almost 24 hours. In the future we intend to increase the frequency of this calculation so that
it is no more than 6 hours out of date.

