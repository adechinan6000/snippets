## RecyclerAdapter

```bash
public class MyRecyclerAdapter extends RecyclerView.Adapter<MyRecyclerAdapter.MuscleViewHolder> {

    static Context context;
    private List<Muscle> muscles;

    public MyRecyclerAdapter(Context context,List<Muscle> muscles) {
        this.muscles = new ArrayList<Muscle>();
        this.context = context;
        this.muscles.addAll(muscles);
    }

    @Override
    public MuscleViewHolder onCreateViewHolder(ViewGroup viewGroup, int i) {
        View itemView = LayoutInflater.
                from(viewGroup.getContext()).
                inflate(R.layout.card_view, viewGroup, false);

        return new MuscleViewHolder(itemView);
    }

    @Override
    public void onBindViewHolder(MuscleViewHolder muscleViewHolder, int i) {
        Muscle muscle = muscles.get(i);
        muscleViewHolder.name.setText(muscle.getName());
        muscleViewHolder.imageID.setImageResource(muscle.getImageID());

    }

    @Override
    public int getItemCount() {
        return muscles.size();
    }


    public static class MuscleViewHolder extends RecyclerView.ViewHolder implements View.OnClickListener{

        protected TextView name;
        protected ImageView imageID;
        protected CardView card;

  

        public MuscleViewHolder(View itemView) {
            super(itemView);
            name = (TextView) itemView.findViewById(R.id.title);
            imageID = (ImageView)itemView.findViewById(R.id.thumbnail);
            card = (CardView) itemView;
            itemView.setOnClickListener(this);
        }

        @Override
        public void onClick(View view) {
        }


        class MyMenuItemClickListener implements PopupMenu.OnMenuItemClickListener {

            public MyMenuItemClickListener() {
            }

            @Override
            public boolean onMenuItemClick(MenuItem menuItem) {
                switch (menuItem.getItemId()) {
                    case R.id.in:
                        Toast.makeText(context, "Add to favourite", Toast.LENGTH_SHORT).show();
                        return true;
                    case R.id.en:
                        Toast.makeText(context, "Play next", Toast.LENGTH_SHORT).show();
                        return true;
                    default:
                }
                return false;
            }
        }
    }


 }

```