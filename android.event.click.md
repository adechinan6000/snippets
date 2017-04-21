# Handling event

* implement : View.OnClickListener
* set listener : button.setOnClickListener(this);
* update onClick function:

```bash
    @Override
    public void onClick(View view) {

        final int id = view.getId();
        switch (id) {
            case R.id.godate: // button reference
                Intent intent = new Intent(this, Main2Activity.class);
                startActivity(intent);
                break;
            case R.id.gorec:
                Intent intent2 = new Intent(this, Main5Activity.class);
                startActivity(intent2);
                break;
        }
    }
```