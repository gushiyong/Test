# Test
这是一个测试项目

 Handler mHandler = new Handler() {
        @Override
        public void handleMessage(Message msg) {
            int position = msg.what;
            int width = getCurrentRadioViewWidth(position);
            fromXDelta = toXDelta;
            // 设置下划线的宽度
            layoutParams = (LinearLayout.LayoutParams) mViewSlider.getLayoutParams();
            layoutParams.width = width;
            mViewSlider.setLayoutParams(layoutParams);
            // 设置下划线移动位置
            toXDelta = getToXDelta(position);
            mCurrentRadioView = position;
            translateSlider(fromXDelta, toXDelta);
        }
    };
    
    private void translateSlider(float fromXDelta, float toXDelta) {
        TranslateAnimation animation = new TranslateAnimation(fromXDelta, toXDelta, 0, 0);
        animation.setDuration(200);
        animation.setFillAfter(true);
        mViewSlider.startAnimation(animation);
    }
