
----------



#1.跳转应用市场评价#
    Uri uri = Uri.parse("market://details?id=" + getActivity().getPackageName());
    Intent intent = new Intent(Intent.ACTION_VIEW,uri);
    intent.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK);
    startActivity(intent);
    

