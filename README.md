# UpdateCheck
Checks for update on remote server -- MUST BE MANUALLY MODIFIED FOR YOUR OWN USE

Working Example:

```
using (UpdateCheck update = new UpdateCheck())
{
    if (update.tryCheck("1.0", 3, "na"))
    {
        if (!update.latest())
        {
            var dialogResult = MessageBox.Show(update.success(), "Update Found", MessageBoxButton.YesNo);
            if ((dialogResult == MessageBoxResult.Yes))
            {
                Process.Start(update.URL());
            }
        }
    }
    else
    {
        MessageBox.Show(update.error(), "An error was encountered");
    }
}
```
which returns the following JSON in its request:
`{"error":0,"software_name":"Factorio Save Manager","software_date_created":"2015-11-25 00:09:15","software_date_last_update":"2015-11-25 00:09:15","software_latest_version":"1.0","kh_id":"http:\/\/www.factorioforums.com\/forum\/download\/file.php?id=6942&sid=dfcd45f2c5f036a824b9301deadbe6fd","is_latest":true,"is_hotfix":0}`
