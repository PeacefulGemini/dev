# log
NEWGS-21661 = 1
NEWGS-21819 = 3
day off = 0.5


# 需做
1. 领券中心下滑，优惠券被遮住



# 问题

     	val pattern = "((http|https):\\/\\/[\\w\\-_]+(\\.[\\w\\-_]+)+([\\w\\-\\.,@?^=%&amp;:/~\\+#]*[\\w\\-\\@?^=%&amp;/~\\+#])?)"
     	val urlText = "完步计划没https://v.youku.com/v_show/id_XNTk1NDE1MjY5Mg==.html?spm=a2hja.149197凯有此问题"
        val r = Pattern.compile(pattern)
        val m = r.matcher(urlText)
        while (m.find()) {
            println(m.group())
        }

完整的文字信息显示没有显示完整的文字信息显示没有显示完整的文字信息显示没有显示完整的文字信息显示没有显示完步计划没https://v.youku.com/v_show/id_XNTk1NDE1MjY5Mg==.html?spm=a2hja.149197凯有此问题凯有此问题凯有此问题凯有此问题凯有此问题凯有此问题凯有此问题凯有此问题凯