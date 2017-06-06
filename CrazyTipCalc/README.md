Special Note

I have received many questions about the lines:

private static final String TOTAL_BILL = “TOTAL_BILL”;
private static final String CURRENT_TIP = “CURRENT_TIP”;
private static final String BILL_WITHOUT_TIP = “BILL_WITHOUT_TIP”;

and then also lines:

billBeforeTip = savedInstanceState.getDouble(BILL_WITHOUT_TIP);
tipAmount = savedInstanceState.getDouble(CURRENT_TIP);
finalBill = savedInstanceState.getDouble(TOTAL_BILL);

and also lines:

outState.putDouble(TOTAL_BILL, finalBill);
outState.putDouble(CURRENT_TIP, tipAmount);
outState.putDouble(BILL_WITHOUT_TIP, billBeforeTip);

What I think is confusing everyone is the final in

private static final String TOTAL_BILL = “TOTAL_BILL”;

The value isn’t stored in TOTAL_BILL, TOTAL_BILL stores the name for the key that is associated with value. These are key value pairs. I should have pointed that out better.

Then when putDouble(String key, double value) is called it inserts a double value into the Bundle, and replaces the value for the given key.

I hope that clears that up. Sorry about any confusion.

If you are having trouble with the SeekBar

If your app is crashing when you use the seekbar it is because I don’t except commas in the price. Make sure you enter a period before the change amount and you should have anymore crashes. Sorry about that.