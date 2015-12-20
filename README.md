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
