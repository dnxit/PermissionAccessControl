# PermissionAccessControl

This is a GitHub repo containing example code that goes with two articles
- [A better way to handle authorization in ASP.NET Core](https://www.thereformedprogrammer.net/a-better-way-to-handle-authorization-in-asp-net-core/).
- [Handling data authorization ASP.NET Core and Entity Framework Core](#)

It contains a ASP.NET Core applications with extra code to implement feature or data authorization.
All the ASP.NET Core applications use in-memory databases which are seeded on startup so it should run anywhere.


MIT licence.

## Feature authorization

The [TestWebApp](https://github.com/JonPSmith/PermissionAccessControl/tree/master/TestWebApp)
is the application you can run to try out the feature authorization code in the article
[A better way to handle authorization in ASP.NET Core](https://www.thereformedprogrammer.net/a-better-way-to-handle-authorization-in-asp-net-core/).

Select the [TestWebApp](https://github.com/JonPSmith/PermissionAccessControl/tree/master/TestWebApp)
as your startup application. When you run it you will see a list of users that you can log in as.
Here are some comments on these:

- Staff@g1.com: 
   - This user can  read the data in the Color controller, but can't change it (you get a "Access denied" error)
   - This user has "bought" access to Feature1, so a "Feature1" link is added to the nav block.
- Manager@g1.com:
   - This user can  read and write the data in the Color controller.
   - This user hasn't "bought" access to Feature1, so no link appears (and you get an "Access denied" error if you try to access it).

## Data authorization

The [DataAuthWebApp](#) 
is the application you can run to try out the data authorization code in the article
[Handling data authorization ASP.NET Core and Entity Framework Core](#).

Select the [DataAuthWebApp](#)
as your startup application. When you run it you will see a list of users that you can log in as.
Here are some comments on these:

- Any user:
   - If you log in you can create some personal data via the "Personal Data" link in the nav block. That data is protected so only the user that created it can see it.  
_Remember - its a in-memory database so it loses anything you put in when it stops._
- Users D4u@g1.com, S4u@g1.com, T4u@g1.com, and Power@g1.com
   - These users access each access a different shop. You can list the shop's stock via the "Shop Stock" link in the nav bar.
- 4uMan@g1.com:
   - This use is a district manager for the three ...4U shops. That user can list the stock in all three shops. This shows how hierarchical access can be set up.

