# PowerShell
Admin PowerScripts

This PowerShell script retrieves information about an Active Directory (AD) user and the expiration of their password. Here’s a breakdown of what the script does:

1. **Define Username Variable**: The script starts by assigning a username to the `$username` variable (e.g., `"UserName"`).
   
2. **Get Last Password Set Time**: The `Get-ADUser` cmdlet is used to retrieve the specified AD user's information, specifically the `PasswordLastSet` property. This provides the timestamp when the user's password was last set.

3. **Retrieve User Information & Password Expiry**: The script then fetches additional information for the same user by querying the `DisplayName` and `msDS-UserPasswordExpiryTimeComputed` properties. 
   - `DisplayName` is the full name of the user.
   - `msDS-UserPasswordExpiryTimeComputed` represents the computed expiration time of the user's password, stored as a file time value.

4. **Select and Format Output**: The `Select-Object` cmdlet is used to format the output:
   - It returns the `DisplayName` property.
   - It converts the `msDS-UserPasswordExpiryTimeComputed` (file time) to a human-readable date format and labels this as `ExpiryDate`.

The script ultimately outputs the user's display name and the computed password expiry date in a readable format.
