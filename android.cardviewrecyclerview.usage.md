## Add this to OnCreate method of an activity


```bash
RecyclerView recyclerView = (RecyclerView) rootView.findViewById(R.id.recyclerList);
recyclerView.setLayoutManager(new GridLayoutManager(this,2));
recyclerView.addItemDecoration(new GridSpacingItemDecoration(2, dpToPx(10), true));
recyclerView.setItemAnimator(new DefaultItemAnimator());
recyclerView.setAdapter(new MyRecyclerAdapter(this, generateMuscles()));
```

## Then add this in class activity

```bash
private ArrayList<Muscle> generateMuscles(){
        ArrayList<Muscle> muscles = new ArrayList<>();
        muscles.add(new Muscle("Deltoide", R.drawable.m1));
        muscles.add(new Muscle("Pubien", R.drawable.m2));
        muscles.add(new Muscle("Procérus", R.drawable.m3));
        muscles.add(new Muscle("Risorius", R.drawable.m4));
        muscles.add(new Muscle("Mentonier", R.drawable.m5));
        muscles.add(new Muscle("Buccinateur", R.drawable.m6));
        muscles.add(new Muscle("sus-maxillo", R.drawable.m7));
        muscles.add(new Muscle("pharyngien", R.drawable.m8));
        muscles.add(new Muscle("Vocal", R.drawable.m9));
        muscles.add(new Muscle("longus", R.drawable.m10));
        return muscles;
}
```

## And this in class activity

```bash
/**
     * RecyclerView item decoration - give equal margin around grid item
     */
    public class GridSpacingItemDecoration extends RecyclerView.ItemDecoration {

        private int spanCount;
        private int spacing;
        private boolean includeEdge;

        public GridSpacingItemDecoration(int spanCount, int spacing, boolean includeEdge) {
            this.spanCount = spanCount;
            this.spacing = spacing;
            this.includeEdge = includeEdge;
        }

        @Override
        public void getItemOffsets(Rect outRect, View view, RecyclerView parent, RecyclerView.State state) {
            int position = parent.getChildAdapterPosition(view); // item position
            int column = position % spanCount; // item column

            if (includeEdge) {
                outRect.left = spacing - column * spacing / spanCount; // spacing - column * ((1f / spanCount) * spacing)
                outRect.right = (column + 1) * spacing / spanCount; // (column + 1) * ((1f / spanCount) * spacing)

                if (position < spanCount) { // top edge
                    outRect.top = spacing;
                }
                outRect.bottom = spacing; // item bottom
            } else {
                outRect.left = column * spacing / spanCount; // column * ((1f / spanCount) * spacing)
                outRect.right = spacing - (column + 1) * spacing / spanCount; // spacing - (column + 1) * ((1f /    spanCount) * spacing)
                if (position >= spanCount) {
                    outRect.top = spacing; // item top
                }
            }
        }
    }

    /**
     * Converting dp to pixel
     */
    private int dpToPx(int dp) {
        Resources r = getResources();
        return Math.round(TypedValue.applyDimension(TypedValue.COMPLEX_UNIT_DIP, dp, r.getDisplayMetrics()));
    }
```