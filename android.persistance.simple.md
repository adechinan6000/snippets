## Save

```bash

SharedPreferences sharedpreferences = getSharedPreferences("user_prefs", 0);  
// 0 - for private mode
Editor editor = sharedpreferences.edit();
editor.putString("cle_string", "monString");
editor.commit();

```

## Get

```bash

SharedPreferences sharedpreferences = getSharedPreferences("user_prefs", 0);
String myString = sharedpreferences.getString("cle_string", null);
title.setText(myString);

```

## Checking

```bash

if (sharedPreferences.contains("cle_string") && sharedPreferences.contains("cle_string2")) {}

```