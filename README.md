
----------



#1.跳转应用市场评价#
    Uri uri = Uri.parse("market://details?id=" + getActivity().getPackageName());
    Intent intent = new Intent(Intent.ACTION_VIEW,uri);
    intent.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK);
    startActivity(intent);


#2.启动模式#
	standard  aunchMode的默认值

	singleTop  调用的目标Activity已经位于调用者的Task的栈顶，则不创建新实例，而是使用当前的这个Activity实例

	singleTask  使用singleTask启动模式的Activity在系统中只会存在一个实例

	singleInstance  singleInstance Activity实例的Task只能存放一个该模式的Activity实例。

#3.获取时间#
	System.currentTimeMillis()

#4.获取签名
	private String getSign(Context context) {  //获得签名
	PackageManager pm = context.getPackageManager();
	List<PackageInfo> apps = pm.getInstalledPackages(PackageManager.GET_SIGNATURES);
	Iterator<PackageInfo> iter = apps.iterator();
	    while(iter.hasNext()) {
	        PackageInfo packageinfo = iter.next();
	String packageName = packageinfo.packageName;
	        if (packageName=="com.diandao.ddandroid"){
	
	return packageinfo.signatures[0].toCharsString();
	}
	    }
	return null;
	}

