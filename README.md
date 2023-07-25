
- 由于字体文件尺寸过大，就没有包括在本git库里面，需要单独下载。下面是大部分项目用到的字体文件清单
- 不同的项目，用的字体不一样，详见 convertJson2Code.py 和 generateTopCharsFont.py
- 这些开源字体，主要在 https://fonts.google.com/ 和 https://fontawesome.com/, https://github.com/google/material-design-icons 等地方下载
- 查询fontawesome的可用字符，可以在这里：https://fontawesome.com/search?o=r&m=free&s=regular%2Csolid
- 查询MaterialIcons的可用字符，可以在这里：https://fonts.google.com/icons?icon.set=Material+Icons
- 如果下载下来的字体格式不正确，需要用到otf2ttf或ttf2otf工具进行转换。
- otf转ttf：
```
pip install otf2ttf
otf2ttf MyFont.otf 
```
- ttf转otf：
```
sudo apt install fontforge
fontforge -lang=py -c 'import fontforge; font = fontforge.open("MyFont.ttf"); font.generate("MyFont.otf")'
```
```
-rw-r--r--@  1 roger  staff   632372 Dec  8  2021 FontAwesome6-Solid+Brands+Regular.ttf
https://github.com/lvgl/lvgl/blob/master/scripts/built_in_font/FontAwesome5-Solid%2BBrands%2BRegular.woff
-rw-r--r--@  1 roger  staff    73332 Dec 15  2010 Lato-Bold.ttf
https://fonts.google.com/specimen/Lato?query=Lato
-rw-r--r--@  1 roger  staff   339168 Nov 10  2022 MaterialIconsOutlined-Regular.otf

-rw-r--r--@  1 roger  staff    32336 Dec 19  2011 MedulaOne-Regular.ttf
https://fonts.google.com/specimen/Medula+One
```
```
-rw-r--r--@  1 roger  staff  4896876 Jan 29  2015 NotoSansJP-Black.otf
-rw-r--r--@  1 roger  staff  4691348 Jan 29  2015 NotoSansJP-Bold.otf
-rw-r--r--@  1 roger  staff  4513716 Jan 29  2015 NotoSansJP-Light.otf
-rw-r--r--@  1 roger  staff  4564400 Jan 29  2015 NotoSansJP-Medium.otf
-rw-r--r--@  1 roger  staff  4548148 Jan 29  2015 NotoSansJP-Regular.otf
-rw-r--r--@  1 roger  staff  4243504 Jan 29  2015 NotoSansJP-Thin.otf
https://fonts.google.com/noto/specimen/Noto+Sans+JP
```
```
-rw-r--r--@  1 roger  staff  8950680 Oct 22  2018 NotoSansSC-Black.otf
-rw-r--r--@  1 roger  staff  8716332 Oct 22  2018 NotoSansSC-Bold.otf
-rw-r--r--@  1 roger  staff  8434156 Oct 22  2018 NotoSansSC-Light.otf
-rw-r--r--@  1 roger  staff  8508520 Oct 22  2018 NotoSansSC-Medium.otf
-rw-r--r--@  1 roger  staff  8481960 Oct 22  2018 NotoSansSC-Regular.otf
-rw-r--r--@  1 roger  staff  7815960 Oct 22  2018 NotoSansSC-Thin.otf
https://fonts.google.com/noto/specimen/Noto+Sans+SC
```
```
-rw-r--r--@  1 roger  staff   169352 Jun 26  2012 RobotoCondensed-Bold.ttf
-rw-r--r--@  1 roger  staff   175420 Jun 26  2012 RobotoCondensed-BoldItalic.ttf
-rw-r--r--@  1 roger  staff   174736 Jun 26  2012 RobotoCondensed-Italic.ttf
-rw-r--r--@  1 roger  staff   167568 Jun 26  2012 RobotoCondensed-Light.ttf
-rw-r--r--@  1 roger  staff   174908 Jun 26  2012 RobotoCondensed-LightItalic.ttf
-rw-r--r--@  1 roger  staff   169848 Jun 26  2012 RobotoCondensed-Regular.ttf
https://fonts.google.com/specimen/Roboto+Condensed?query=Robot
```
```
-rw-r--r--@  1 roger  staff    37292 Apr  4  2012 RussoOne-Regular.ttf
https://fonts.google.com/specimen/Russo+One
```
```
-rw-r--r--@  1 roger  staff   282904 Jun 25  2014 Teko-Bold.ttf
-rw-r--r--@  1 roger  staff   279608 Jun 25  2014 Teko-Light.ttf
-rw-r--r--@  1 roger  staff   287712 Jun 25  2014 Teko-Medium.ttf
-rw-r--r--@  1 roger  staff   289336 Jun 25  2014 Teko-Regular.ttf
-rw-r--r--@  1 roger  staff   294932 Jun 25  2014 Teko-SemiBold.ttf
https://fonts.google.com/specimen/Teko?query=Teko
```

- 另外，`npm install` 可以安装lv_font_conv工具到 node_modules；但是由于这个工具版本比较低，不支持lvgl 9，所以把手工修改后的(lv_table_head.js)工具直接添加到了git库里面，因此就不需要再npm install了

- 关于fontawesome，之前的FontAwesome5-Solid+Brands+Regular.woff，可以从网上搜索并下载到；但是 FontAwesome6-Solid+Brands+Regular.ttf 需要手动创建，方法是：

# 下载：
wget https://use.fontawesome.com/releases/v6.2.0/fontawesome-free-6.2.0-web.zip
unzip fontawesome-free-6.2.0-web.zip
# 合并：
python3 merge_fonts.py -d fontawesome-free-6.2.0-web/webfonts  -o FontAwesome6-Solid+Brands+Regular.ttf
```
