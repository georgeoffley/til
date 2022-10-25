# Using Variables with Shared Queries

When you make shared queries with variables you can also use those variables in apps.

When you create the shared queries you make sure to add in variables like this `{{ user-id }}`.

![Setting in query library](../../images/setting-query-lib-retool.png)

You then need to make sure to fill out variables when you import them into the app. So when you click on the query you set `{{ user_id }}` as the value. 

![Setting variable in the imported app query](../../images/import-query-in-app-retool.png)

Then you are able to use things like `additionalScope` when triggering queries.

![Using additionalScope in tigger functions](../../images/additional-scope-retool.png)


#GeneralTools 
	#Retool 