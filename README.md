
import android.content.Intent;
import android.os.Build;
import android.os.Bundle;
import android.support.v7.app.AppCompatActivity;
import android.support.v7.widget.Toolbar;
import android.view.View;
import android.widget.ImageView;
import android.widget.TextView;

import com.marriagehall.seller.R;


public class MyAccountActivity extends AppCompatActivity {

    private Toolbar toolbar;
    private TextView sellerNameTV, userTypeTV, descriptionTV, mobileNoTV, cellPhoneTV,
            emailIdTV, addressTV, countyTV, regionTV, cityTV, websiteTV;
    private ImageView editInfoIV;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_my_account);

        toolbar = (Toolbar) findViewById(R.id.toolbar);
        setSupportActionBar(toolbar);
        getSupportActionBar().setDisplayHomeAsUpEnabled(true);

        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.LOLLIPOP) {
            getWindow().setStatusBarColor(getResources().getColor(R.color.colorPrimaryDark));
        }

        initAll();
    }

    private void initAll() {

        sellerNameTV = (TextView) findViewById(R.id.sellerNameTV);
        userTypeTV = (TextView) findViewById(R.id.userTypeTV);
        descriptionTV = (TextView) findViewById(R.id.descriptionTV);
        mobileNoTV = (TextView) findViewById(R.id.mobileNoTV);
        cellPhoneTV = (TextView) findViewById(R.id.cellPhoneTV);
        emailIdTV = (TextView) findViewById(R.id.emailIdTV);
        addressTV = (TextView) findViewById(R.id.addressTV);
        countyTV = (TextView) findViewById(R.id.countyTV);
        regionTV = (TextView) findViewById(R.id.regionTV);
        cityTV = (TextView) findViewById(R.id.cityTV);
        websiteTV = (TextView) findViewById(R.id.websiteTV);

        editInfoIV = (ImageView) findViewById(R.id.editInfoIV);

        eventClickListener();
    }

    private void eventClickListener() {
        editInfoIV.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Intent intent = new Intent(MyAccountActivity.this, EditMyAccountActivity.class);
                startActivity(intent);
            }
        });
    }
}
