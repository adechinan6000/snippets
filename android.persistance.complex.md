## dependencies

```bash
Insert Your Code Here.
```

## Sauvegarder un objet

```bash
SharedPreferences sharedPreferences = context.getSharedPreferences("PREFS", Context.MODE_PRIVATE);
Gson gson = new Gson();
 
User user = ...; //on veut sauvegarder cet objet
 
sharedPreferences.edit()
     .putString("user",gson.toJson(user))
     .apply();
```

## Charger un objet

```bash
SharedPreferences sharedPreferences = context.getSharedPreferences("PREFS", Context.MODE_PRIVATE);
Gson gson = new Gson();
 
String json = sharedPreferences.getString("user",null);
 
User user = null;
if(json != null)
    user = gson.fromJson(json,User.class);
```

## Sauvegarder une liste

```bash
SharedPreferences sharedPreferences = context.getSharedPreferences("PREFS", Context.MODE_PRIVATE);
Gson gson = new Gson();
 
List<User> users = ...; //on veut sauvegarder ces objets
 
sharedPreferences.edit()
     .putString("users",gson.toJson(users))
     .apply();
```

## Charger une liste

```bash
SharedPreferences sharedPreferences = context.getSharedPreferences("PREFS", Context.MODE_PRIVATE);
Gson gson = new Gson();
 
String json = sharedPreferences.getString("users",null);
 
List<User> users = null;
if(json != null)
    user = gson.fromJson(json,new TypeToken<List<User>>() {}.getType());
```