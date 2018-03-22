# schedulePlan
一个简单的日历，可以添加工作的考勤，日程的安排，就100多行代码，直接拿来用
第一步:  直接导入布局文件view_amount_editor
第二步： 在activity中或者fragment中填充进来，我这里是在activity中
        
        View view = UiUtils.inflateView(R.layout.view_amount_editor);//用自己的填充方法
        ImageView ivDelete = (ImageView) view.findViewById(R.id.iv_delete);
        productName = (TextView) view.findViewById(R.id.tv_product_name);
        tvAmount = (TextView) view.findViewById(R.id.tv_amount);
        TextView tv0 = (TextView) view.findViewById(R.id.tv_0);
        TextView tv1 = (TextView) view.findViewById(R.id.tv_1);
        TextView tv2 = (TextView) view.findViewById(R.id.tv_2);
        TextView tv3 = (TextView) view.findViewById(R.id.tv_3);
        TextView tv4 = (TextView) view.findViewById(R.id.tv_4);
        TextView tv5 = (TextView) view.findViewById(R.id.tv_5);
        TextView tv6 = (TextView) view.findViewById(R.id.tv_6);
        TextView tv7 = (TextView) view.findViewById(R.id.tv_7);
        TextView tv8 = (TextView) view.findViewById(R.id.tv_8);
        TextView tv9 = (TextView) view.findViewById(R.id.tv_9);
        TextView tvc = (TextView) view.findViewById(R.id.tv_c);
        TextView tv_ = (TextView) view.findViewById(R.id.tv_);
        TextView tv_goback = (TextView) view.findViewById(R.id.tv_goback);
        TextView tvOk = (TextView) view.findViewById(R.id.tv_ok);
        tv0.setOnClickListener(this);
        tv1.setOnClickListener(this);
        tv2.setOnClickListener(this);
        tv3.setOnClickListener(this);
        tv4.setOnClickListener(this);
        tv5.setOnClickListener(this);
        tv6.setOnClickListener(this);
        tv7.setOnClickListener(this);
        tv8.setOnClickListener(this);
        tv9.setOnClickListener(this);
        tvc.setOnClickListener(this);
        tv_.setOnClickListener(this);
        tvOk.setOnClickListener(this);
        tv_goback.setOnClickListener(this);
        ivDelete.setOnClickListener(this);
第三步：  设置点击事件       



    @Override
    public void onClick(View v) {
        switch (v.getId()){
            case R.id.iv_delete: 
                return;
            case R.id.tv_ok: 
                return;
        }
        switch (v.getId()) {
            case R.id.tv_1:
                mAmount.append("1");
                break;
            case R.id.tv_2:
                mAmount.append("2");
                break;
            case R.id.tv_3:
                mAmount.append("3");
                break;
            case R.id.tv_4:
                mAmount.append("4");
                break;
            case R.id.tv_5:
                mAmount.append("5");
                break;
            case R.id.tv_6:
                mAmount.append("6");
                break;
            case R.id.tv_7:
                mAmount.append("7");
                break;
            case R.id.tv_8:
                mAmount.append("8");
                break;
            case R.id.tv_9:
                mAmount.append("9");
                break;
            case R.id.tv_:
                mAmount.append(".");
                break;
            case R.id.tv_0:
                mAmount.append("0");
                break;
            case R.id.tv_c:
                if (mAmount.toString().length() > 0){
                    mAmount.delete(0, mAmount.toString().length());
                }
                break;
            case R.id.tv_goback:
                if (mAmount.toString().length()>0) {
                    mAmount.deleteCharAt(mAmount.toString().length() - 1);
                }
                break;

        }
        tvAmount.setText(mAmount.toString());
    }
    private StringBuilder mAmount=new StringBuilder();
  第四步  放到你的
  
        private BottomSheetDialog dialog;
            dialog.setContentView(view);
        
