# open-multiscreen-activity

used for displaying 2 activities in 2 screens

## Install

```bash
npm install open-multiscreen-activity
npx cap sync
```

## API

<docgen-index>

* [`echo(...)`](#echo)
* [`openSplitScreen(...)`](#opensplitscreen)

</docgen-index>

<docgen-api>
<!--Update the source file JSDoc comments and rerun docgen to update the docs below-->

### echo(...)

```typescript
echo(options: { value: string; }) => Promise<{ value: string; }>
```

| Param         | Type                            |
| ------------- | ------------------------------- |
| **`options`** | <code>{ value: string; }</code> |

**Returns:** <code>Promise&lt;{ value: string; }&gt;</code>

--------------------


### openSplitScreen(...)

```typescript
openSplitScreen(options: { video1Url: string; video2Url: string; }) => any
```

| Param         | Type                                                   |
| ------------- | ------------------------------------------------------ |
| **`options`** | <code>{ video1Url: string; video2Url: string; }</code> |

**Returns:** <code>any</code>

--------------------

</docgen-api>

add this in ionic App's manifest file
```
 <!-- Declare plugin activities here -->
      <activity android:name="com.test.plugins.multiscreenactivity.SplitScreenActivity"
        android:configChanges="keyboardHidden|orientation|screenSize"
        android:launchMode="singleTop"
        android:resizeableActivity="true"
        android:screenOrientation="fullSensor">
      </activity>

      <activity
        android:name="com.test.plugins.multiscreenactivity.SecondScreenActivity"
        android:configChanges="keyboardHidden|orientation|screenSize"
        android:launchMode="singleTop"
        android:resizeableActivity="true"
        android:screenOrientation="fullSensor"
        android:exported="true">

        <intent-filter>
          <action android:name="com.test.plugins.multiscreenactivity.SWAP_FRAGMENTS" />
          <category android:name="android.intent.category.DEFAULT" />
        </intent-filter>
      </activity>

      <receiver android:name="com.test.plugins.multiscreenactivity.SwapReceiver"
        android:exported="true">
        <intent-filter>
          <action android:name="com.test.plugins.multiscreenactivity.SWAP_FRAGMENTS" />
        </intent-filter>
      </receiver>
```
