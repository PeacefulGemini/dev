# log
meeting = 0.5
meeting = 1

1.5 6.5

# 需做
1. dialog测试
2. 旋转屏幕测试
3. webview测试

# 问题
        Context newContext;
        DisplayMetrics displayMetrics = baseContext.getResources().getDisplayMetrics();
        final float targetDensity = (float) (displayMetrics.widthPixels / 360);
        final int targetDensityDpi = (int) (160 * targetDensity);

        Configuration configuration = baseContext.getResources().getConfiguration();
        configuration.densityDpi = targetDensityDpi;

        newContext = baseContext.createConfigurationContext(configuration);
        super.attachBaseContext(newContext);
