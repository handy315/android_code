package com.roinchina.current.utils;

import android.annotation.TargetApi;
import android.app.Activity;
import android.graphics.drawable.Drawable;
import android.os.Build;
import android.view.Gravity;
import android.view.View;
import android.widget.LinearLayout;
import android.widget.TextView;
import android.widget.Toast;

import com.roinchina.current.R;
import com.roinchina.current.base.BaseAplication;
import com.roinchina.current.beans.UserInfo;


public class MyToastUtils {
    private static Toast mToast;
    private static int mTime = 3000;
    private static Activity activity;

    @TargetApi(Build.VERSION_CODES.JELLY_BEAN)
    public static void toast(String message) {

        activity = BaseAplication.getInstanse().getCurrentActivity();
        if (mToast == null) {
            mToast = Toast.makeText(BaseAplication.getInstanse().getCurrentActivity(), message, Toast.LENGTH_SHORT);
        } else {
            mToast.setText(message);
            mToast.setDuration(Toast.LENGTH_SHORT);
        }
        mToast.setGravity(Gravity.CENTER, 0, 0);
        LinearLayout layout = (LinearLayout) mToast.getView();
        TextView toastTextView = (TextView) layout.findViewById(android.R.id.message);
        Drawable background = toastTextView.getBackground();

        String manufacturersType = UserInfo.getInstance().getManufacturersType();
        if (manufacturersType.trim().equals("MX4 Pro")) {
            toastTextView.setBackground(null);
            layout.setBackgroundResource(R.drawable.bg_toast_bg);
            layout.setPadding((int) activity.getResources().getDimension(R.dimen.base_dimen_10), (int) activity.getResources().getDimension(R.dimen.base_dimen_25)
                    , (int) activity.getResources().getDimension(R.dimen.base_dimen_10), (int) activity.getResources().getDimension(R.dimen.base_dimen_25));
        }else{
            layout.setBackgroundResource(R.drawable.bg_toast_bg);
        }
        mToast.setView(layout);

        mToast.show();
    }


}
