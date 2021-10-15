## 1-Glide  
加载视频第一帧数做封面
``` kotlin
fun setThumbImage(imageView: ImageView, url: String?) {
    val drawable=getDrawable(R.drawable.default_background)
    val colorDrawable = ColorDrawable(imageView.context.getColor(R.color.color_c5cee0))
    if (url.isNullOrEmpty()) {
        Glide.with(imageView)
            .load(drawable)
            .into(imageView)
    } else {
        Glide.with(imageView)
            .setDefaultRequestOptions(
                RequestOptions().frame(1000000)
                    .placeholder(colorDrawable)
                    .error(drawable)
            )
            .load(url)
            .error(drawable)
            .into(imageView)
    }
}
```