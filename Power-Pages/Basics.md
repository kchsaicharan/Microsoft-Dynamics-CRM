# Enable Sign In Page in Power Pages
  Navigate to site settings from Portal Management App and set two following existing records values as 'true'.
    set record with name "Profile/Enabled" value as 'true'
    set record with name "Authentication/LoginTrackingEnabled" value as 'true'
    and create new record with name "Authentication/UserManager/UserValidator/RequireUniqueEmail" value as 'true'

# Show plugin/workflow error message to user in power pages 
  Under site settings Create a record with name "Site/EnableCustomPluginError" value as 'true'
