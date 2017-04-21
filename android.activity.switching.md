# Switching beetween activity

```bash
@Override
    public void onClick(View view) {

        Intent intent = new Intent(view.getContext(), Main2Activity.class);
        intent.putExtra("extra_text","hello"); // textView2.setText(getIntent().getStringExtra("extra_text"));
        view.getContext().startActivity(intent);

    }
```