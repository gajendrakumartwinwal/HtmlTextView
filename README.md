HtmlTextView
============

Android Text view with Html text with all tags supported

How to use:-

You will be provided a list of Views in same order as appeared in string and you can use them wherever you want to use.


	ArrayList<View> htmlViews = new ArrayList<View>();
			htmlViews = HtmlStringParser.getHtmlView(context, Your Html String, new OnTagEncountered() {

				@Override
				public View getView(String element) {
					View returnViews;
					if(element.contains("<img"))
						returnViews = getImageViewForString(mInflater, element);
					else if(element.contains("<video"))
						returnViews = getVideoViewForString(mContext, mInflater, element);
					else if(element.contains("<iframe"))
						returnViews = getIframeViewForString(mInflater, element);
					else
						returnViews = null;
					return returnViews;
				}
			}, "img", "video", "iframe");
