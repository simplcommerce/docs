# Notes on Entity Framework Migration

---

To keep the code clean, we will periodly clean up the Migrations folder. We intend to have only 1 migration file per a release, starting to 1.0.0.
That mean for the release 1.0.0 we will merge all the existsing migration into one file. Similarly for the next release after 1.0.0, let say 1.1.0 for example, we will merge all the migration since 1.0.0 into one file and so on.
 
There is no problem to migrate your database if you follow our offical releases. However, it's a little tricky if you use the code before our offical releases. If that is the case, then you can follow workarounds below.

### If the data is not important

Simply just delete the existing database and create it again.

### If the data is imporatant.

Open the [__EFMigrationsHistory] table, get the latest MigrationId, then base on the git commit history try to get the SimplDbContextModelSnapshot.cs at that MigrationId, then delete all the files in Migrations folder, paste the SimplDbContextModelSnapshot.cs at the MigrationId you have just got. Run Add-Migration, it will generate changes from that MigrationId to now
