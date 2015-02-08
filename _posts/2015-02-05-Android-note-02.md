
#Android笔记


##Android匹配查询关键字后变色


	public View getView(final int position, View convertView, ViewGroup parent) {
		// 附合查询条件字体变色
	
		// ......
		int index;
		String search = et_search.getText().toString().trim();// 关键字
		ForegroundColorSpan span = new ForegroundColorSpan(ctx.getResources().getColor(R.color.bg_green));// 要显示的颜色
		SpannableStringBuilder builder = new SpannableStringBuilder(item.id);
	
		index = item.id.indexOf(search);// 从第几个匹配上
		if (index != -1) {// 有这个关键字用builder显示
			builder.setSpan(span, index, index + search.length(), Spannable.SPAN_EXCLUSIVE_EXCLUSIVE);
			holder.tv_man_item_id.setText(builder);
		} else {// 没有则直接显示
			holder.tv_man_item_id.setText(item.id);
		}
	}

[Android 匹配查询关键字后变色][1]


[1]: http://blog.sina.com.cn/s/blog_3e333c4a0102vmba.html


