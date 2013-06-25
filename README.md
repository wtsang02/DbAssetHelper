DbAssetHelper
=============

Import/export sqlite Database From asset or sd card. Single class that does the job.

Common use of export in Activity class:


  @Override
	public boolean onCreateOptionsMenu(Menu menu) {
		menu.add("Export Database");
		return super.onCreateOptionsMenu(menu);
	}

	@Override
	public boolean onOptionsItemSelected(MenuItem item) {
		switch (item.getItemId()) {
		case 0:
			new AssetDatabaseHelper(this,"test.sqlite").exportDatabase("/_REU/test.sqlite");
			return true;
		default:
			return super.onOptionsItemSelected(item);
		}
	}
  
  
  //Or on pause:
  @Override
	protected void onPause() {
  	new AssetDatabaseHelper(this,"test.sqlite").exportDatabase("/_REU/test.sqlite");
		super.onPause();
	}
