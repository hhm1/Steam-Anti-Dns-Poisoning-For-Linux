<p style="text-align: left;">本文档<span style="color: #000000;">适用于</span>Ubuntu，Debian、RedHat、CentOS及其它衍生系统，测试系统为Ubuntu18.04，CentOS7.9</p>

<ul>
 	<li>
<h2>自动安装</h2>
</li>
 	<li><code>wget wget.haoming.gq/install-ubuntu.sh</code></li>
 	<li>Redhat及其衍生系统输入</li>
 	<li><code>wget wget.haoming.gq/install-centos.sh</code></li>
 	<li><a href="#run">点击跳转到安装后运行</a></li>
</ul>
&nbsp;
<ul>
 	<li>
<h2>手动安装</h2>
</li>
 	<li>首先，防踩坑</li>
</ul>
<ul>
 	<li class="hl"><code class="">sudo apt update</code></li>
 	<li>RedHat及其衍生系统</li>
 	<li>
<pre class="code">yum update</pre>
</li>
</ul>
&nbsp;
<ul>
 	<li>安装好必需的库</li>
 	<li>
<pre class="hl"><code class="">sudo apt-get install openssl libssl-dev
sudo apt-get install libpcre3 libpcre3-dev
sudo apt-get install zlib1g-dev</code></pre>
</li>
 	<li>RedHat（CentOS）及其衍生系统输入以下指令</li>
 	<li>
<pre class="code">yum install pcre pcre-devel openssl openssl-devel zlib zlib-devel gcc wget</pre>
</li>
</ul>
&nbsp;
<ul>
 	<li>之后，下载文件</li>
 	<li><code class="">wget wget.haoming.gq/steam-anti-dns-poisoning-main-for-linux.tar.gz</code></li>
</ul>
&nbsp;
<ul>
 	<li>解压</li>
 	<li>
<pre class="hl"><code class="">tar -xf steam-anti-dns-poisoning-main-for-linux.tar.gz</code></pre>
</li>
</ul>
&nbsp;
<ul>
 	<li>加载文件夹</li>
 	<li>
<pre class="hl"><code class="">cd steam-anti-dns-poisoning-main-for-linux</code></pre>
</li>
</ul>
&nbsp;
<ul>
 	<li>安装nginx</li>
 	<li>
<pre class="code">./configure --prefix=/usr/local/nginx --with-openssl=/usr/local/openssl-1.0.1 --with-http_ssl_module</pre>
</li>
 	<li>RedHat（CentOS）及其衍生系统使用以下命令</li>
 	<li>
<pre class="code">./configure --prefix=/usr/local/nginx  --with-http_ssl_module</pre>
</li>
</ul>
&nbsp;
<ul>
 	<li>安装完成之后，将证书和hosts导入</li>
 	<li>
<pre class="hl"><code class="">sudo cp rootCA.crt /usr/local/share/ca-certificates</code></pre>
<h2></h2>
<pre class="hl"><code class="">echo hosts &gt;&gt; /etc/hosts
</code></pre>
</li>
 	<li>RedHat（CentOS）及其衍生系统输入</li>
 	<li>
<pre class="code">cp rootCA.cet /etc/pki/ca-trust/source/anchors/</pre>
</li>
 	<li><code class="">echo hosts &gt;&gt; /etc/hosts</code></li>
</ul>
&nbsp;
<ul>
 	<li>RedHat（CentOS）及其衍生系统附加指令（我不知道为啥Ubuntu会附带压缩包里面的文件一起复制过去，而CentOS不行（恼））</li>
 	<li>
<pre class="code">cp -r conf /usr/local/nginx</pre>
</li>
</ul>
&nbsp;
<ul>
 	<li id="run">大功告成！Debian、Ubuntu及其衍生系统输入
<pre class="code">nginx</pre>
即可使用，RedHat（CentOS）及其衍生系统输入
<pre class="code">/usr/local/nginx/sbin/nginx</pre>
</li>
 	<li>如果有错误的话欢迎指正</li>
</ul>
&nbsp;

&nbsp;
