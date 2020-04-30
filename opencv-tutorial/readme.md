<!DOCTYPE html>
<html lang="en-US">
<head >
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>OpenCV Tutorial: A Guide to Learn OpenCV - PyImageSearch</title>

<!-- This site is optimized with the Yoast SEO plugin v13.0 - https://yoast.com/wordpress/plugins/seo/ -->
<meta name="description" content="In this tutorial you&#039;ll learn the basics of the OpenCV library. I&#039;ll gently guide you through the fundamentals and help you learn OpenCV."/>
<meta name="robots" content="max-snippet:-1, max-image-preview:large, max-video-preview:-1"/>
<link rel="canonical" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/" />
<meta property="og:locale" content="en_US" />
<meta property="og:type" content="article" />
<meta property="og:title" content="OpenCV Tutorial: A Guide to Learn OpenCV - PyImageSearch" />
<meta property="og:description" content="In this tutorial you&#039;ll learn the basics of the OpenCV library. I&#039;ll gently guide you through the fundamentals and help you learn OpenCV." />
<meta property="og:url" content="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/" />
<meta property="og:site_name" content="PyImageSearch" />
<meta property="article:tag" content="basics" />
<meta property="article:tag" content="blurring" />
<meta property="article:tag" content="computer vision basics" />
<meta property="article:tag" content="contours" />
<meta property="article:tag" content="edge detection" />
<meta property="article:tag" content="opencv" />
<meta property="article:tag" content="resizing" />
<meta property="article:tag" content="rotating" />
<meta property="article:tag" content="thresholding" />
<meta property="article:section" content="Tutorials" />
<meta property="article:published_time" content="2018-07-19T13:44:01+00:00" />
<meta property="article:modified_time" content="2020-04-18T18:35:20+00:00" />
<meta property="og:updated_time" content="2020-04-18T18:35:20+00:00" />
<meta property="og:image" content="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_header.jpg" />
<meta property="og:image:secure_url" content="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_header.jpg" />
<meta property="og:image:width" content="600" />
<meta property="og:image:height" content="375" />
<script type='application/ld+json' class='yoast-schema-graph yoast-schema-graph--main'>{"@context":"https://schema.org","@graph":[{"@type":"WebSite","@id":"https://www.pyimagesearch.com/#website","url":"https://www.pyimagesearch.com/","name":"PyImageSearch","description":"You can master Computer Vision, Deep Learning, and OpenCV - PyImageSearch","potentialAction":{"@type":"SearchAction","target":"https://www.pyimagesearch.com/?s={search_term_string}","query-input":"required name=search_term_string"}},{"@type":"ImageObject","@id":"https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#primaryimage","url":"https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_header.jpg","width":600,"height":375},{"@type":"WebPage","@id":"https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#webpage","url":"https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/","inLanguage":"en-US","name":"OpenCV Tutorial: A Guide to Learn OpenCV - PyImageSearch","isPartOf":{"@id":"https://www.pyimagesearch.com/#website"},"primaryImageOfPage":{"@id":"https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#primaryimage"},"datePublished":"2018-07-19T13:44:01+00:00","dateModified":"2020-04-18T18:35:20+00:00","author":{"@id":"https://www.pyimagesearch.com/#/schema/person/5901b399e2f20b986362a00636181cca"},"description":"In this tutorial you'll learn the basics of the OpenCV library. I'll gently guide you through the fundamentals and help you learn OpenCV."},{"@type":["Person"],"@id":"https://www.pyimagesearch.com/#/schema/person/5901b399e2f20b986362a00636181cca","name":"Adrian Rosebrock","image":{"@type":"ImageObject","@id":"https://www.pyimagesearch.com/#authorlogo","url":"https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&d=mm&r=g","caption":"Adrian Rosebrock"},"description":"Hi there, I\u2019m Adrian Rosebrock, PhD. All too often I see developers, students, and researchers wasting their time, studying the wrong things, and generally struggling to get started with Computer Vision, Deep Learning, and OpenCV. I created this website to show you what I believe is the best possible way to get your start.","sameAs":[]}]}</script>
<!-- / Yoast SEO plugin. -->

<link rel='dns-prefetch' href='//www.google.com' />
<link rel='dns-prefetch' href='//a.opmnstr.com' />
<link rel='dns-prefetch' href='//use.typekit.net' />
<link rel='dns-prefetch' href='//s.w.org' />
<link rel="alternate" type="application/rss+xml" title="PyImageSearch &raquo; Feed" href="https://www.pyimagesearch.com/feed/" />
<link rel="alternate" type="application/rss+xml" title="PyImageSearch &raquo; Comments Feed" href="https://www.pyimagesearch.com/comments/feed/" />
<link rel="alternate" type="application/rss+xml" title="PyImageSearch &raquo; OpenCV Tutorial: A Guide to Learn OpenCV Comments Feed" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/feed/" />
<link rel="stylesheet" href="https://www.pyimagesearch.com/wp-content/cache/minify/7034b.css" media="all" />








<link rel='stylesheet' id='pyimagesearch-fonts-css'  href='https://use.typekit.net/aay3jsp.css?ver=5.3.2' type='text/css' media='all' />
<link rel="stylesheet" href="https://www.pyimagesearch.com/wp-content/cache/minify/b9c43.css" media="all" />



<script src="https://www.pyimagesearch.com/wp-content/cache/minify/c7035.js"></script>

<script type='text/javascript' data-cfasync="false" id="omapi-script" async="async" src='https://a.opmnstr.com/app/js/api.min.js'></script>
<link rel='https://api.w.org/' href='https://www.pyimagesearch.com/wp-json/' />
<link rel="EditURI" type="application/rsd+xml" title="RSD" href="https://www.pyimagesearch.com/xmlrpc.php?rsd" />
<link rel="wlwmanifest" type="application/wlwmanifest+xml" href="https://www.pyimagesearch.com/wp-includes/wlwmanifest.xml" /> 
<meta name="generator" content="WordPress 5.3.2" />
<link rel='shortlink' href='https://www.pyimagesearch.com/?p=7642' />
<link rel="alternate" type="application/json+oembed" href="https://www.pyimagesearch.com/wp-json/oembed/1.0/embed?url=https%3A%2F%2Fwww.pyimagesearch.com%2F2018%2F07%2F19%2Fopencv-tutorial-a-guide-to-learn-opencv%2F" />
<link rel="alternate" type="text/xml+oembed" href="https://www.pyimagesearch.com/wp-json/oembed/1.0/embed?url=https%3A%2F%2Fwww.pyimagesearch.com%2F2018%2F07%2F19%2Fopencv-tutorial-a-guide-to-learn-opencv%2F&#038;format=xml" />
    <script type="text/javascript">
        var ajaxurl = 'https://www.pyimagesearch.com/wp-admin/admin-ajax.php';
    </script>
<link rel="pingback" href="https://www.pyimagesearch.com/xmlrpc.php" />
<style type="text/css">
/* <![CDATA[ */
img.latex { vertical-align: middle; border: none; }
/* ]]> */
</style>
		<style type="text/css" id="wp-custom-css">
			.grecaptcha-badge {
    display: none !important;
}

img.latex {
	margin: 0!important;
	display: inline!important;
}

.entry-content > .aligncenter {
	margin-left: auto;
	margin-right: auto;
} 		</style>
		</head>
<body class="post-template-default single single-post postid-7642 single-format-standard wp-embed-responsive header-full-width content-sidebar genesis-breadcrumbs-hidden genesis-footer-widgets-visible"><div class="site-container"><ul class="genesis-skip-link"><li><a href="#genesis-nav-primary" class="screen-reader-shortcut"> Skip to primary navigation</a></li><li><a href="#genesis-content" class="screen-reader-shortcut"> Skip to main content</a></li><li><a href="#genesis-sidebar-primary" class="screen-reader-shortcut"> Skip to primary sidebar</a></li><li><a href="#genesis-footer-widgets" class="screen-reader-shortcut"> Skip to footer</a></li></ul><header class="site-header"><div class="wrap"><div class="title-area"><p class="site-title"><a href="https://www.pyimagesearch.com/">PyImageSearch</a></p><p class="site-description">You can master Computer Vision, Deep Learning, and OpenCV - PyImageSearch</p></div><nav class="nav-secondary" aria-label="Secondary"><div class="wrap"><ul id="menu-header-secondary" class="menu genesis-nav-menu menu-secondary"><li id="menu-item-12816" class="menu-item"><a href="https://www.pyimagesearch.com/about/"><span >About</span></a></li>
<li id="menu-item-12817" class="menu-item"><a href="https://www.pyimagesearch.com/faqs/"><span >FAQ</span></a></li>
<li id="menu-item-12818" class="menu-item"><a href="https://www.pyimagesearch.com/contact/"><span >Contact</span></a></li>
</ul></div></nav><div class="main-nav-wrap"><nav class="nav-primary" aria-label="Main" id="genesis-nav-primary"><ul id="menu-main-menu" class="menu genesis-nav-menu menu-primary"><li id="menu-item-11459" class="menu-item"><a href="https://www.pyimagesearch.com/start-here/"><span >Get Started</span></a></li>
<li id="menu-item-10696" class="is-topics menu-item menu-item-has-children"><a href="/topics/"><span >Topics</span></a><span class="submenu-expand" tabindex="-1"><svg class="svg-icon" width="16" height="16" aria-hidden="true" role="img" focusable="false" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512"><path d="M151.5 347.8L3.5 201c-4.7-4.7-4.7-12.3 0-17l19.8-19.8c4.7-4.7 12.3-4.7 17 0L160 282.7l119.7-118.5c4.7-4.7 12.3-4.7 17 0l19.8 19.8c4.7 4.7 4.7 12.3 0 17l-148 146.8c-4.7 4.7-12.3 4.7-17 0z"/></svg></span>
<ul class="sub-menu">
	<li id="menu-item-10698" class="has-icon has-icon--deep-learning menu-item"><a href="https://www.pyimagesearch.com/category/deep-learning/"><span >Deep Learning</span></a></li>
	<li id="menu-item-10699" class="has-icon has-icon--dlib menu-item"><a href="https://www.pyimagesearch.com/category/dlib/"><span >Dlib Library</span></a></li>
	<li id="menu-item-10700" class="has-icon has-icon--iot menu-item"><a href="https://www.pyimagesearch.com/category/embedded/"><span >Embedded/IoT and Computer Vision</span></a></li>
	<li id="menu-item-10701" class="has-icon has-icon--face menu-item"><a href="https://www.pyimagesearch.com/category/faces/"><span >Face Applications</span></a></li>
	<li id="menu-item-10702" class="has-icon has-icon--image menu-item"><a href="https://www.pyimagesearch.com/category/image-processing/"><span >Image Processing</span></a></li>
	<li id="menu-item-10703" class="has-icon has-icon--interviews menu-item"><a href="https://www.pyimagesearch.com/category/interviews/"><span >Interviews</span></a></li>
	<li id="menu-item-10704" class="has-icon has-icon--keras menu-item"><a href="https://www.pyimagesearch.com/category/keras-and-tensorflow/"><span >Keras and TensorFlow</span></a></li>
	<li id="menu-item-10705" class="has-icon has-icon--ml menu-item"><a href="https://www.pyimagesearch.com/category/machine-learning/"><span >Machine Learning and Computer Vision</span></a></li>
	<li id="menu-item-10706" class="has-icon has-icon--medical menu-item"><a href="https://www.pyimagesearch.com/category/medical/"><span >Medical Computer Vision</span></a></li>
	<li id="menu-item-10707" class="has-icon has-icon--ocr menu-item"><a href="https://www.pyimagesearch.com/category/optical-character-recognition-ocr/"><span >Optical Character Recognition (OCR)</span></a></li>
	<li id="menu-item-10708" class="has-icon has-icon--object-detection menu-item"><a href="https://www.pyimagesearch.com/category/object-detection/"><span >Object Detection</span></a></li>
	<li id="menu-item-10709" class="has-icon has-icon--object-tracking menu-item"><a href="https://www.pyimagesearch.com/category/object-tracking/"><span >Object Tracking</span></a></li>
	<li id="menu-item-10711" class="has-icon has-icon--opencv menu-item"><a href="https://www.pyimagesearch.com/category/opencv/"><span >OpenCV Tutorials</span></a></li>
	<li id="menu-item-10710" class="has-icon has-icon--pi menu-item"><a href="https://www.pyimagesearch.com/category/raspberry-pi/"><span >Raspberry Pi</span></a></li>
</ul>
</li>
<li id="menu-item-12831" class="menu-item"><a href="https://www.pyimagesearch.com/books-and-courses/"><span >Books and Courses</span></a></li>
<li id="menu-item-2615" class="menu-item"><a href="https://www.pyimagesearch.com/opencv-tutorials-resources-guides/"><span >OpenCV Install Guides</span></a></li>
<li id="menu-item-12845" class="menu-item current_page_parent"><a href="https://www.pyimagesearch.com/blog/"><span >Blog</span></a></li>
<li id="menu-item-2619" class="mobile-only menu-item"><a href="https://www.pyimagesearch.com/about/"><span >About</span></a></li>
<li id="menu-item-10258" class="mobile-only menu-item"><a href="https://www.pyimagesearch.com/faqs/"><span >FAQ</span></a></li>
<li id="menu-item-6744" class="mobile-only menu-item"><a href="https://www.pyimagesearch.com/contact/"><span >Contact</span></a></li>
</ul></nav><div class="header-search"><button class="mobile-search-toggle"><svg class="svg-icon search-icon" width="28" height="28" aria-hidden="true" role="img" focusable="false" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M508.5 468.9L387.1 347.5c-2.3-2.3-5.3-3.5-8.5-3.5h-13.2c31.5-36.5 50.6-84 50.6-136C416 93.1 322.9 0 208 0S0 93.1 0 208s93.1 208 208 208c52 0 99.5-19.1 136-50.6v13.2c0 3.2 1.3 6.2 3.5 8.5l121.4 121.4c4.7 4.7 12.3 4.7 17 0l22.6-22.6c4.7-4.7 4.7-12.3 0-17zM208 368c-88.4 0-160-71.6-160-160S119.6 48 208 48s160 71.6 160 160-71.6 160-160 160z"/></svg><svg class="svg-icon search-close" width="28" height="28" aria-hidden="true" role="img" focusable="false" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512"><path d="M207.6 256l107.72-107.72c6.23-6.23 6.23-16.34 0-22.58l-25.03-25.03c-6.23-6.23-16.34-6.23-22.58 0L160 208.4 52.28 100.68c-6.23-6.23-16.34-6.23-22.58 0L4.68 125.7c-6.23 6.23-6.23 16.34 0 22.58L112.4 256 4.68 363.72c-6.23 6.23-6.23 16.34 0 22.58l25.03 25.03c6.23 6.23 16.34 6.23 22.58 0L160 303.6l107.72 107.72c6.23 6.23 16.34 6.23 22.58 0l25.03-25.03c6.23-6.23 6.23-16.34 0-22.58L207.6 256z"/></svg><span class="screen-reader-text">Search</span></button>
<form role="search" method="get" class="search-form" action="https://www.pyimagesearch.com/">
	<label>
		<span class="screen-reader-text">Search...</span>
		<input type="search" class="search-field" placeholder="Search articles..." value="" name="s" title="Search for" />
	</label>
	<button type="submit" class="search-submit"><svg class="svg-icon search" width="20" height="20" aria-hidden="true" role="img" focusable="false" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M508.5 468.9L387.1 347.5c-2.3-2.3-5.3-3.5-8.5-3.5h-13.2c31.5-36.5 50.6-84 50.6-136C416 93.1 322.9 0 208 0S0 93.1 0 208s93.1 208 208 208c52 0 99.5-19.1 136-50.6v13.2c0 3.2 1.3 6.2 3.5 8.5l121.4 121.4c4.7 4.7 12.3 4.7 17 0l22.6-22.6c4.7-4.7 4.7-12.3 0-17zM208 368c-88.4 0-160-71.6-160-160S119.6 48 208 48s160 71.6 160 160-71.6 160-160 160z"/></svg><span class="screen-reader-text">Submit</span></button>
</form>
</div><nav class="nav-mobile"><button class="mobile-menu-toggle"><span class="mobile-menu-open"><svg class="svg-icon menu-open" width="13" height="13" aria-hidden="true" role="img" focusable="false" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M436 124H12c-6.627 0-12-5.373-12-12V80c0-6.627 5.373-12 12-12h424c6.627 0 12 5.373 12 12v32c0 6.627-5.373 12-12 12zm0 160H12c-6.627 0-12-5.373-12-12v-32c0-6.627 5.373-12 12-12h424c6.627 0 12 5.373 12 12v32c0 6.627-5.373 12-12 12zm0 160H12c-6.627 0-12-5.373-12-12v-32c0-6.627 5.373-12 12-12h424c6.627 0 12 5.373 12 12v32c0 6.627-5.373 12-12 12z"/></svg>Menu</span><span class="mobile-menu-close"><svg class="svg-icon menu-close" width="13" height="13" aria-hidden="true" role="img" focusable="false" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512"><path d="M207.6 256l107.72-107.72c6.23-6.23 6.23-16.34 0-22.58l-25.03-25.03c-6.23-6.23-16.34-6.23-22.58 0L160 208.4 52.28 100.68c-6.23-6.23-16.34-6.23-22.58 0L4.68 125.7c-6.23 6.23-6.23 16.34 0 22.58L112.4 256 4.68 363.72c-6.23 6.23-6.23 16.34 0 22.58l25.03 25.03c6.23 6.23 16.34 6.23 22.58 0L160 303.6l107.72 107.72c6.23 6.23 16.34 6.23 22.58 0l25.03-25.03c6.23-6.23 6.23-16.34 0-22.58L207.6 256z"/></svg>Close</span><span class="screen-reader-text">Menu</span></button></nav></div></div></header><div class="pyi-page-hero"><div class="wrap"><p class="entry-meta"><span class="entry-categories"><a href="https://www.pyimagesearch.com/category/getting-started/" rel="category tag">Getting Started</a> <a href="https://www.pyimagesearch.com/category/tutorials/" rel="category tag">Tutorials</a></span></p><header class="entry-header"><h1 class="entry-title">OpenCV Tutorial: A Guide to Learn OpenCV</h1>
</header><p class="entry-meta">by <span class="entry-author"><a href="https://www.pyimagesearch.com/author/adrian/" class="entry-author-link" rel="author"><span class="entry-author-name">Adrian Rosebrock</span></a></span> on <time class="entry-time">July 19, 2018</time></p><div class="pyi-hero-left"></div><div class="pyi-hero-right"></div></div></div><div class="site-inner"><div class="wrap"><div class="content-sidebar-wrap"><main class="content" id="genesis-content"><article class="post-7642 post type-post status-publish format-standard has-post-thumbnail category-getting-started category-tutorials tag-basics tag-blurring tag-computer-vision-basics tag-contours tag-edge-detection tag-opencv tag-resizing tag-rotating tag-thresholding entry"><div class="entry-content">
<div class="single-post-sticky-spacer">
	<div id="source-code-mini-wrap" class="gpd-source-code-mini single-post-top-cta" style="">
   		<div class="gpd-source-code-mini-content">
			<a href="#download-the-code" id="pyis-optinmonster-open-modal">
			Click here to download the source code to this post			</a>
    	</div>
	</div>
</div><p><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_header.jpg"><img class="aligncenter size-full wp-image-7648" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_header.jpg" alt="" width="600" height="375" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_header.jpg 600w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_header-300x188.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" /></a></p>
<p>Whether you’re interested in learning how to apply facial recognition to video streams, building a complete deep learning pipeline for image classification, or simply want to tinker with your Raspberry Pi and add image recognition to a hobby project, <strong>you’ll need to learn OpenCV somewhere along the way.</strong></p>
<p>The truth is that learning OpenCV <em>used</em> to be quite challenging. The documentation was hard to navigate. The tutorials were hard to follow and incomplete. And even some of the books were a bit tedious to work through.</p>
<p>The good news is learning OpenCV isn’t as hard as it used to be. And in fact, I’ll go as far as to say studying OpenCV has become <em>significantly easier.</em></p>
<p>And to prove it to you (and help you learn OpenCV), I’ve put together this complete guide to learning the fundamentals of the OpenCV library using the Python programming language.</p>
<p><strong>Let’s go ahead and get started learning the basics of OpenCV and image processing. By the end of today’s blog post, you’ll understand the fundamentals of OpenCV.</strong></p>
<div id="pyi-source-code-block" class="source-code-wrap"><div class="gpd-source-code">
    <div class="gpd-source-code-content">
        <img src="//www.pyimagesearch.com/wp-content/uploads/2020/01/source-code-icon.png" alt="">
        <h4>Looking for the source code to this post?</h4>
                    <a href="#download-the-code">Jump Right To The Downloads Section <svg class="svg-icon arrow-right" width="12" height="12" aria-hidden="true" role="img" focusable="false" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M6.8125 0.1875C6.875 0.125 6.96875 0.09375 7.09375 0.09375C7.1875 0.09375 7.28125 0.125 7.34375 0.1875L13.875 6.75C13.9375 6.8125 14 6.90625 14 7C14 7.125 13.9375 7.1875 13.875 7.25L7.34375 13.8125C7.28125 13.875 7.1875 13.9062 7.09375 13.9062C6.96875 13.9062 6.875 13.875 6.8125 13.8125L6.1875 13.1875C6.125 13.125 6.09375 13.0625 6.09375 12.9375C6.09375 12.8438 6.125 12.75 6.1875 12.6562L11.0312 7.8125H0.375C0.25 7.8125 0.15625 7.78125 0.09375 7.71875C0.03125 7.65625 0 7.5625 0 7.4375V6.5625C0 6.46875 0.03125 6.375 0.09375 6.3125C0.15625 6.25 0.25 6.1875 0.375 6.1875H11.0312L6.1875 1.34375C6.125 1.28125 6.09375 1.1875 6.09375 1.0625C6.09375 0.96875 6.125 0.875 6.1875 0.8125L6.8125 0.1875Z" fill="#169FE6"></path></svg></a>
            </div>
</div>
</div>
<h2>OpenCV Tutorial: A Guide to Learn OpenCV</h2>
<p>This OpenCV tutorial is for beginners just getting started learning the basics. Inside this guide, you’ll learn basic image processing operations using the OpenCV library using Python.</p>
<p>And by the end of the tutorial you’ll be putting together a complete project to count basic objects in images using contours.</p>
<p>While this tutorial is aimed at beginners just getting started with image processing and the OpenCV library, I encourage you to give it a read even if you have a bit of experience.</p>
<p>A quick refresher in OpenCV basics will help you with your own projects as well.</p>
<h3>Installing OpenCV and imutils on your system</h3>
<p>The first step today is to install OpenCV on your system (if you haven’t already).</p>
<p>I maintain an <a href="https://pyimagesearch.com/opencv-tutorials-resources-guides/" target="_blank" rel="noopener noreferrer"><strong>OpenCV Install Tutorials</strong></a> page which contains links to previous OpenCV installation guides for Ubuntu, macOS, and Raspberry Pi.</p>
<p>You should visit that page and find + follow the appropriate guide for your system.</p>
<p>Once your fresh OpenCV development environment is set up, <strong>install the imutils package via pip. </strong>I have created and maintained <code class="EnlighterJSRAW" data-enlighter-language="python">imutils</code>  (<a href="https://github.com/jrosebr1/imutils" target="_blank" rel="noopener noreferrer">source on GitHub</a>) for the image processing community and it is used heavily on my blog. You should install <code class="EnlighterJSRAW" data-enlighter-language="python">imutils</code>  in the same environment you installed OpenCV into &#8212; you&#8217;ll need it to work through this blog post as it will facilitate basic image processing operations:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="shell" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="2">
$ pip install imutils
</pre>

<p><em><strong>Note:</strong></em> <em>If you are using Python virtual environments don&#8217;t forget to use the <code class="EnlighterJSRAW" data-enlighter-language="python">workon</code>  command to enter your environment before installing <code class="EnlighterJSRAW" data-enlighter-language="python">imutils</code> !</em></p>
<h3>OpenCV Project Structure</h3>
<p>Before going too far down the rabbit hole, be sure to grab the code + images from the <em><strong>&#8220;Downloads&#8221;</strong></em> section of today&#8217;s blog post.</p>
<p>From there, navigate to where you downloaded the .zip in your terminal (<code class="EnlighterJSRAW" data-enlighter-language="python">cd</code> ). And then we can <code class="EnlighterJSRAW" data-enlighter-language="shell">unzip</code>  the archive, change working directories (<code class="EnlighterJSRAW" data-enlighter-language="shell">cd</code> ) into the project folder, and analyze the project structure via <code class="EnlighterJSRAW" data-enlighter-language="python">tree</code> :</p>

<pre class="EnlighterJSRAW" data-enlighter-language="shell" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="9">
$ cd ~/Downloads
$ unzip opencv-tutorial.zip
$ cd opencv-tutorial
$ tree
.
├── jp.png
├── opencv_tutorial_01.py
├── opencv_tutorial_02.py
└── tetris_blocks.png

0 directories, 4 files
</pre>

<p>In this tutorial we’ll be creating two Python scripts to help you learn OpenCV basics:</p>
<ol>
<li>Our first script, <code class="EnlighterJSRAW" data-enlighter-language="shell">opencv_tutorial_01.py</code>   will cover basic image processing operations using an image from the movie, <em>Jurassic Park</em> ( <code class="EnlighterJSRAW" data-enlighter-language="shell">jp.png</code> ).</li>
<li>From there, <code class="EnlighterJSRAW" data-enlighter-language="shell">opencv_tutorial_02.py</code>  will show you how to use these image processing building blocks to create an OpenCV application to count the number of objects in a Tetris image (<code class="EnlighterJSRAW" data-enlighter-language="shell">tetris_blocks.png</code> ).</li>
</ol>
<h3>Loading and displaying an image</h3>
<figure id="attachment_7649" aria-describedby="caption-attachment-7649" style="width: 600px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_load_image.jpg"><img class="wp-image-7649 size-full" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_load_image.jpg" alt="" width="600" height="384" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_load_image.jpg 600w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_load_image-300x192.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" /></a><figcaption id="caption-attachment-7649" class="wp-caption-text"><strong>Figure 1:</strong> Learning OpenCV basics with Python begins with loading and displaying an image &#8212; a simple process that requires only a few lines of code.</figcaption></figure>
<p>Let&#8217;s begin by opening up <code class="EnlighterJSRAW" data-enlighter-language="shell">opencv_tutorial_01.py</code>  in your favorite text editor or IDE:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="15">
# import the necessary packages
import imutils
import cv2

# load the input image and show its dimensions, keeping in mind that
# images are represented as a multi-dimensional NumPy array with
# shape no. rows (height) x no. columns (width) x no. channels (depth)
image = cv2.imread("jp.png")
(h, w, d) = image.shape
print("width={}, height={}, depth={}".format(w, h, d))

# display the image to our screen -- we will need to click the window
# open by OpenCV and press a key on our keyboard to continue execution
cv2.imshow("Image", image)
cv2.waitKey(0)
</pre>

<p>On <strong>Lines 2 and 3</strong> we import both <code class="EnlighterJSRAW" data-enlighter-language="python">imutils</code>  and <code class="EnlighterJSRAW" data-enlighter-language="python">cv2</code> . The <code class="EnlighterJSRAW" data-enlighter-language="python">cv2</code>  package is OpenCV and despite the 2 embedded, it can actually be OpenCV 3 (or possibly OpenCV 4 which may be released later in 2018). The <code class="EnlighterJSRAW" data-enlighter-language="python">imutils</code>  package is my series of convenience functions.</p>
<p>Now that we have the required software at our fingertips via imports, let&#8217;s load an image from disk into memory.</p>
<p>To load our <em>Jurassic Park</em> image (from one of my favorite movies), we call <code class="EnlighterJSRAW" data-enlighter-language="python">cv2.imread("jp.png")</code> . As you can see on <strong>Line 8</strong>, we assign the result to <code class="EnlighterJSRAW" data-enlighter-language="python">image</code> . Our <code class="EnlighterJSRAW" data-enlighter-language="python">image</code>  is actually just a NumPy array.</p>
<p>Later in this script, we&#8217;ll need the height and width. So on <strong>Line 9</strong>, I call <code class="EnlighterJSRAW" data-enlighter-language="python">image.shape</code>  to extract the height, width, and depth.</p>
<p>It may seem confusing that the height comes before the width, but think of it this way:</p>
<ul>
<li>We describe matrices by <em># of rows x # of columns</em></li>
<li>The number of <em>rows</em> is our <em>height</em></li>
<li>And the number of <em>columns</em> is our <em>width</em></li>
</ul>
<p>Therefore, the dimensions of an image represented as a NumPy array are actually represented as <em>(height, width, depth).</em></p>
<p>Depth is the number of channels &#8212; in our case this is three since we&#8217;re working with 3 color channels: Blue, Green, and Red.</p>
<p>The print command shown on <strong>Line 10</strong> will output the values to the terminal:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="shell" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="24">
width=600, height=322, depth=3
</pre>

<p>To display the image on the screen using OpenCV we employ <code class="EnlighterJSRAW" data-enlighter-language="python">cv2.imshow("Image", image)</code>  on <strong>Line 14</strong>. The subsequent line waits for a keypress (<strong>Line 15</strong>). This is important otherwise our image would display and disappear faster than we&#8217;d even see the image.</p>
<p><em><strong>Note:</strong></em> <em>You need to actually click the active window opened by OpenCV and press a key on your keyboard to advance the script. OpenCV cannot monitor your terminal for input so if you a press a key in the terminal OpenCV will not notice. Again, you will need to click the active OpenCV window on your screen and press a key on your keyboard.</em></p>
<h3>Accessing individual pixels</h3>
<figure id="attachment_7917" aria-describedby="caption-attachment-7917" style="width: 600px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/06/opencv_tutorial_gradient_rgb.jpg"><img class="wp-image-7917 size-full" src="https://pyimagesearch.com/wp-content/uploads/2018/06/opencv_tutorial_gradient_rgb.jpg" alt="" width="600" height="300" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/06/opencv_tutorial_gradient_rgb.jpg 600w, https://www.pyimagesearch.com/wp-content/uploads/2018/06/opencv_tutorial_gradient_rgb-300x150.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" /></a><figcaption id="caption-attachment-7917" class="wp-caption-text"><strong>Figure 2:</strong> <em>Top</em>: grayscale gradient where brighter pixels are closer to 255 and darker pixels are closer to 0. <em>Bottom</em>: RGB venn diagram where brighter pixels are closer to the center.</figcaption></figure>
<p>First, you may ask:</p>
<blockquote><p>What is a pixel?</p></blockquote>
<p>All images consist of pixels which are the raw building blocks of images. Images are made of pixels in a grid. A 640 x 480 image has 640 columns (the width) and 480 rows (the height). There are <code class="EnlighterJSRAW" data-enlighter-language="python">640 * 480 = 307200</code>  pixels in an image with those dimensions.</p>
<p>Each pixel in a grayscale image has a value representing the shade of gray. In OpenCV, there are 256 shades of gray &#8212; from 0 to 255. So a grayscale image would have a grayscale value associated with each pixel.</p>
<p>Pixels in a color image have additional information. There are several color spaces that you&#8217;ll soon become familiar with as you learn about image processing. For simplicity let&#8217;s only consider the RGB color space.</p>
<p>In OpenCV color images in the RGB (Red, Green, Blue) color space have a 3-tuple associated with each pixel: <code class="EnlighterJSRAW" data-enlighter-language="python">(B, G, R)</code> .</p>
<p>Notice the ordering is BGR rather than RGB. This is because when OpenCV was first being developed many years ago the standard was BGR ordering. Over the years, the standard has now become RGB but OpenCV still maintains this &#8220;legacy&#8221; BGR ordering to ensure no existing code breaks.</p>
<p>Each value in the BGR 3-tuple has a range of <code class="EnlighterJSRAW" data-enlighter-language="python">[0, 255]</code> . How many color possibilities are there for each pixel in an RGB image in OpenCV? That&#8217;s easy: <code class="EnlighterJSRAW" data-enlighter-language="python">256 * 256 * 256 = 16777216</code> .</p>
<p>Now that we know exactly what a pixel is, let&#8217;s see how to retrieve the value of an individual pixel in the image:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="17" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="30">
# access the RGB pixel located at x=50, y=100, keepind in mind that
# OpenCV stores images in BGR order rather than RGB
(B, G, R) = image[100, 50]
print("R={}, G={}, B={}".format(R, G, B))
</pre>

<p>As shown previously, our image dimensions are <code class="EnlighterJSRAW" data-enlighter-language="python">width=600, height=322, depth=3</code> . We can access individual pixel values in the array by specifying the coordinates so long as they are within the max width and height.</p>
<p>The code, <code class="EnlighterJSRAW" data-enlighter-language="python">image[100, 50]</code> , yields a 3-tuple of BGR values from the pixel located at <code class="EnlighterJSRAW" data-enlighter-language="python">x=50</code>  and <code class="EnlighterJSRAW" data-enlighter-language="python">y=100</code> (again, keep in mind that the <em>height</em> is the number of <em>rows</em> and the <em>width</em> is the number of <em>columns</em> &#8212; take a second now to convince yourself this is true). As stated above, OpenCV stores images in BGR ordering (unlike Matplotlib, for example). Check out how simple it is to extract the color channel values for the pixel on <strong>Line 19</strong>.</p>
<p>The resulting pixel value is shown on the terminal here:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="shell" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="35">
R=41, G=49, B=37
</pre>

<h3>Array slicing and cropping</h3>
<p>Extracting &#8220;regions of interest&#8221; (ROIs) is an important skill for image processing.</p>
<p>Say, for example, you&#8217;re working on recognizing faces in a movie. First, you&#8217;d run a face detection algorithm to find the coordinates of faces in all the frames you&#8217;re working with. Then you&#8217;d want to extract the face ROIs and either save them or process them. Locating all frames containing Dr. Ian Malcolm in <em>Jurassic Park</em> would be a great face recognition mini-project to work on.</p>
<p>For now, let&#8217;s just <em>manually</em> extract an ROI. This can be accomplished with array slicing.</p>
<figure id="attachment_7675" aria-describedby="caption-attachment-7675" style="width: 600px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_array_slicing_and_crop.jpg"><img class="size-full wp-image-7675" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_array_slicing_and_crop.jpg" alt="" width="600" height="358" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_array_slicing_and_crop.jpg 600w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_array_slicing_and_crop-300x179.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" /></a><figcaption id="caption-attachment-7675" class="wp-caption-text"><strong>Figure 3:</strong> Array slicing with OpenCV allows us to extract a region of interest (ROI) easily.</figcaption></figure>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="22" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="36">
# extract a 100x100 pixel square ROI (Region of Interest) from the
# input image starting at x=320,y=60 at ending at x=420,y=160
roi = image[60:160, 320:420]
cv2.imshow("ROI", roi)
cv2.waitKey(0)
</pre>

<p>Array slicing is shown on <strong>Line 24</strong> with the format: <code class="EnlighterJSRAW" data-enlighter-language="python">image[startY:endY, startX:endX]</code> . This code grabs an <code class="EnlighterJSRAW" data-enlighter-language="python">roi</code>  which we then display on <strong>Line 25</strong>. Just like last time, we display until a key is pressed (<strong>Line 26</strong>).</p>
<p>As you can see in <strong>Figure 3</strong>, we&#8217;ve extracted the face of Dr. Ian Malcolm. I actually predetermined the <em>(x, y)</em>-coordinates using Photoshop for this example, but if you stick with me on the blog you could <a href="https://pyimagesearch.com/2018/02/26/face-detection-with-opencv-and-deep-learning/" target="_blank" rel="noopener noreferrer">detect and extract face ROI&#8217;s automatically</a>.</p>
<h3>Resizing images</h3>
<p>Resizing images is important for a number of reasons. First, you might want to resize a large image to fit on your screen. Image processing is also faster on smaller images because there are fewer pixels to process. In the case of deep learning, we often resize images, ignoring aspect ratio, so that the volume fits into a network which requires that an image be square and of a certain dimension.</p>
<p>Let&#8217;s resize our original image to 200 x 200 pixels:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="28" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="39">
# resize the image to 200x200px, ignoring aspect ratio
resized = cv2.resize(image, (200, 200))
cv2.imshow("Fixed Resizing", resized)
cv2.waitKey(0)
</pre>

<p>On <strong>Line 29</strong>, we have resized an image ignoring aspect ratio. <strong>Figure 4</strong> (<em>right</em>) shows that the image is resized but is now distorted because we didn&#8217;t take into account the aspect ratio.</p>
<figure id="attachment_7651" aria-describedby="caption-attachment-7651" style="width: 600px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_resizing.jpg"><img class="wp-image-7651 size-full" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_resizing.jpg" alt="" width="600" height="281" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_resizing.jpg 600w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_resizing-300x141.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" /></a><figcaption id="caption-attachment-7651" class="wp-caption-text"><strong>Figure 4:</strong> Resizing an image with OpenCV and Python can be conducted with <code>cv2.resize</code> however aspect ratio is not preserved automatically.</figcaption></figure>
<p>Let&#8217;s calculate the aspect ratio of the original image and use it to resize an image so that it doesn&#8217;t appear squished and distorted:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="33" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="40">
# fixed resizing and distort aspect ratio so let's resize the width
# to be 300px but compute the new height based on the aspect ratio
r = 300.0 / w
dim = (300, int(h * r))
resized = cv2.resize(image, dim)
cv2.imshow("Aspect Ratio Resize", resized)
cv2.waitKey(0)
</pre>

<p>Recall back to <strong>Line 9 </strong>of this script where we extracted the width and height of the image.</p>
<p>Let&#8217;s say that we want to take our 600-pixel wide image and resize it to 300 pixels wide while <em>maintaining aspect ratio</em>.</p>
<p>On <strong>Line 35</strong> we calculate the ratio of the <em>new width</em> to the <em>old width</em> (which happens to be 0.5).</p>
<p>From there, we specify our dimensions of the new image, <code class="EnlighterJSRAW" data-enlighter-language="python">dim</code> . We know that we want a 300-pixel wide image, but we must calculate the height using the ratio by multiplying <code class="EnlighterJSRAW" data-enlighter-language="python">h</code>  by <code class="EnlighterJSRAW" data-enlighter-language="python">r</code>  (the original height and our ratio respectively).</p>
<p>Feeding <code class="EnlighterJSRAW" data-enlighter-language="python">dim</code>  (our dimensions) into the <code class="EnlighterJSRAW" data-enlighter-language="python">cv2.resize</code>  function, we&#8217;ve now obtained a new image named <code class="EnlighterJSRAW" data-enlighter-language="python">resized</code>  which is not distorted (<b>Line 37</b>).</p>
<p>To check our work, we display the image using the code on <strong>Line 38</strong>:</p>
<figure id="attachment_7653" aria-describedby="caption-attachment-7653" style="width: 600px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_ar_resize.jpg"><img class="size-full wp-image-7653" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_ar_resize.jpg" alt="" width="600" height="347" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_ar_resize.jpg 600w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_ar_resize-300x174.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" /></a><figcaption id="caption-attachment-7653" class="wp-caption-text"><strong>Figure 5:</strong> Resizing images while maintaining aspect ratio with OpenCV is a three-step process: (1) extract the image dimensions, (2) compute the aspect ratio, and (3) resize the image (<code>cv2.resize</code>) along one dimension and multiply the other dimension by the aspect ratio. See <strong>Figure 6</strong> for an even easier method.</figcaption></figure>
<p><strong>But can we make this process of preserving aspect ratio during resizing even easier?</strong></p>
<p>Yes!</p>
<p>Computing the aspect ratio each time we want to resize an image is a bit tedious, so I wrapped the code in a function within <code class="EnlighterJSRAW" data-enlighter-language="python">imutils</code> .</p>
<p>Here is how you may use <code class="EnlighterJSRAW" data-enlighter-language="python">imutils.resize</code> :</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="41" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="49">
# manually computing the aspect ratio can be a pain so let's use the
# imutils library instead
resized = imutils.resize(image, width=300)
cv2.imshow("Imutils Resize", resized)
cv2.waitKey(0)
</pre>

<p>In a single line of code, we&#8217;ve preserved aspect ratio and resized the image.</p>
<p>Simple right?</p>
<p>All you need to provide is your target <code class="EnlighterJSRAW" data-enlighter-language="python">width</code>  or target <code class="EnlighterJSRAW" data-enlighter-language="python">height</code>  as a keyword argument (<strong>Line 43</strong>).</p>
<p>Here&#8217;s the result:</p>
<figure id="attachment_7652" aria-describedby="caption-attachment-7652" style="width: 600px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_imutils_resize.jpg"><img class="size-full wp-image-7652" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_imutils_resize.jpg" alt="" width="600" height="310" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_imutils_resize.jpg 600w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_imutils_resize-300x155.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" /></a><figcaption id="caption-attachment-7652" class="wp-caption-text"><strong>Figure 6:</strong> If you&#8217;d like to maintain aspect ratio while resizing images with OpenCV and Python, simply use <code>imutils.resize</code>. Now your image won&#8217;t risk being &#8220;squished&#8221; as in <strong>Figure 4</strong>.</figcaption></figure>
<h3>Rotating an image</h3>
<p>Let&#8217;s rotate our <em>Jurassic Park</em> image for our next example:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="47" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="52">
# let's rotate an image 45 degrees clockwise using OpenCV by first
# computing the image center, then constructing the rotation matrix,
# and then finally applying the affine warp
center = (w // 2, h // 2)
M = cv2.getRotationMatrix2D(center, -45, 1.0)
rotated = cv2.warpAffine(image, M, (w, h))
cv2.imshow("OpenCV Rotation", rotated)
cv2.waitKey(0)
</pre>

<p>Rotating an image about the center point requires that we first calculate the center <em>(x, y)</em>-coordinates of the image (<strong>Line 50</strong>).</p>
<p><em><strong>Note: </strong>We use <code class="EnlighterJSRAW" data-enlighter-language="python">//</code>  to perform integer math (i.e., no floating point values)</em>.</p>
<p>From there we calculate a rotation matrix, <code class="EnlighterJSRAW" data-enlighter-language="python">M</code>  (<strong>Line 51</strong>). The <code class="EnlighterJSRAW" data-enlighter-language="python">-45</code>  means that we&#8217;ll rotate the image 45 degrees clockwise. Recall from your middle/high school geometry class about the unit circle and you&#8217;ll be able to remind yourself that <strong>positive angles are counterclockwise</strong> and <strong>negative angles are clockwise.</strong></p>
<p>From there we warp the image using the matrix (effectively rotating it) on <strong>Line 52</strong>.</p>
<p>The rotated image is displayed to the screen on <strong>Line 52</strong> and is shown in <strong>Figure 7</strong>:</p>
<figure id="attachment_7654" aria-describedby="caption-attachment-7654" style="width: 600px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_opencv_rotation.jpg"><img class="size-full wp-image-7654" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_opencv_rotation.jpg" alt="" width="600" height="375" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_opencv_rotation.jpg 600w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_opencv_rotation-300x188.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" /></a><figcaption id="caption-attachment-7654" class="wp-caption-text"><strong>Figure 7:</strong> Rotating an image with OpenCV about the center point requires three steps: (1) compute the center point using the image width and height, (2) compute a rotation matrix with <code>cv2.getRotationMatrix2D</code>, and (3) use the rotation matrix to warp the image with <code>cv2.warpAffine</code>.</figcaption></figure>
<p>Now let&#8217;s perform the same operation in just a single line of code using <code class="EnlighterJSRAW" data-enlighter-language="python">imutils</code> :</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="56" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="57">
# rotation can also be easily accomplished via imutils with less code
rotated = imutils.rotate(image, -45)
cv2.imshow("Imutils Rotation", rotated)
cv2.waitKey(0)
</pre>

<p>Since I don&#8217;t have to rotate image as much as resizing them (comparatively) I find the rotation process harder to remember. Therefore, I created a function in <code class="EnlighterJSRAW" data-enlighter-language="python">imutils</code>  to handle it for us. In a single line of code, I can accomplish rotating the image 45 degrees clockwise (<strong>Line 57</strong>) as in <strong>Figure 8:</strong></p>
<figure id="attachment_7656" aria-describedby="caption-attachment-7656" style="width: 600px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_imutils_rotation.jpg"><img class="size-full wp-image-7656" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_imutils_rotation.jpg" alt="" width="600" height="375" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_imutils_rotation.jpg 600w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_imutils_rotation-300x188.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" /></a><figcaption id="caption-attachment-7656" class="wp-caption-text"><strong>Figure 8:</strong> With <code>imutils.rotate</code>, we can rotate an image with OpenCV and Python conveniently with a single line of code.</figcaption></figure>
<p>At this point you have to be thinking:</p>
<blockquote><p>Why in the world is the image clipped?</p></blockquote>
<p>The thing is, OpenCV <em>doesn&#8217;t care</em> if our image is clipped and out of view after the rotation. I find this to be quite bothersome, so here&#8217;s my <code class="EnlighterJSRAW" data-enlighter-language="python">imutils</code>  version which will keep the entire image in view. I call it <code class="EnlighterJSRAW" data-enlighter-language="python">rotate_bound</code> :</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="61" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="61">
# OpenCV doesn't "care" if our rotated image is clipped after rotation
# so we can instead use another imutils convenience function to help
# us out
rotated = imutils.rotate_bound(image, 45)
cv2.imshow("Imutils Bound Rotation", rotated)
cv2.waitKey(0)
</pre>

<p>There&#8217;s a lot going on behind the scenes of <code class="EnlighterJSRAW" data-enlighter-language="python">rotate_bound</code> . If you&#8217;re interested in how the method on <strong>Line 64</strong> works, be sure to check out <a href="https://pyimagesearch.com/2017/01/02/rotate-images-correctly-with-opencv-and-python/" target="_blank" rel="noopener noreferrer">this blog post</a>.</p>
<p>The result is shown in <strong>Figure 9</strong>:</p>
<figure id="attachment_7657" aria-describedby="caption-attachment-7657" style="width: 485px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_bounded_rotation.jpg"><img class="size-full wp-image-7657" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_bounded_rotation.jpg" alt="" width="485" height="500" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_bounded_rotation.jpg 485w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_bounded_rotation-291x300.jpg 291w" sizes="(max-width: 485px) 100vw, 485px" /></a><figcaption id="caption-attachment-7657" class="wp-caption-text"><strong>Figure 9:</strong> The <code>rotate_bound</code> function of <code>imutils</code> will prevent OpenCV from clipping the image during a rotation. See <a href="https://pyimagesearch.com/2017/01/02/rotate-images-correctly-with-opencv-and-python/" target="_blank" rel="noopener noreferrer">this blog post</a> to learn how it works!</figcaption></figure>
<p>Perfect! The entire image is in the frame and it is correctly rotated 45 degrees clockwise.</p>
<h3>Smoothing an image</h3>
<p>In many image processing pipelines, we must blur an image to reduce high-frequency noise, making it easier for our algorithms to detect and understand the actual <em>contents</em> of the image rather than just <em>noise</em> that will &#8220;confuse&#8221; our algorithms. Blurring an image is very easy in OpenCV and there are a number of ways to accomplish it.</p>
<figure id="attachment_7658" aria-describedby="caption-attachment-7658" style="width: 600px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_blurring.jpg"><img class="size-full wp-image-7658" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_blurring.jpg" alt="" width="600" height="375" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_blurring.jpg 600w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_blurring-300x188.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" /></a><figcaption id="caption-attachment-7658" class="wp-caption-text"><strong>Figure 10:</strong> This image has undergone a Gaussian blur with an <code>11 x 11</code> kernel using OpenCV. Blurring is an important step of many image processing pipelines to reduce high-frequency noise.</figcaption></figure>
<p>I often use the <code class="EnlighterJSRAW" data-enlighter-language="python">GaussianBlur</code>  function:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="68" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="64">
# apply a Gaussian blur with a 11x11 kernel to the image to smooth it,
# useful when reducing high frequency noise
blurred = cv2.GaussianBlur(image, (11, 11), 0)
cv2.imshow("Blurred", blurred)
cv2.waitKey(0)
</pre>

<p>On <strong>Line 70</strong> we perform a Gaussian Blur with an 11 x 11 kernel the result of which is shown in <strong>Figure 10</strong>.</p>
<p>Larger kernels would yield a more blurry image. Smaller kernels will create less blurry images. To read more about kernels, refer to <a href="https://pyimagesearch.com/2016/07/25/convolutions-with-opencv-and-python/" target="_blank" rel="noopener noreferrer">this blog post</a> or the <a href="https://pyimagesearch.com/pyimagesearch-gurus/" target="_blank" rel="noopener noreferrer">PyImageSearch Gurus course</a>.</p>
<h3>Drawing on an image</h3>
<p>In this section, we&#8217;re going to draw a rectangle, circle, and line on an input image. We&#8217;ll also overlay text on an image as well.</p>
<p>Before we move on with drawing on an image with OpenCV, take note that <em>drawing operations on images are performed in-place</em>. Therefore at the beginning of each code block, we make a copy of the original image storing the copy as <code class="EnlighterJSRAW" data-enlighter-language="python">output</code> . We then proceed to draw on the image called <code class="EnlighterJSRAW" data-enlighter-language="python">output</code> in-place so we do not destroy our original image.</p>
<p>Let&#8217;s draw a rectangle around Ian Malcolm&#8217;s face:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="74" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="67">
# draw a 2px thick red rectangle surrounding the face
output = image.copy()
cv2.rectangle(output, (320, 60), (420, 160), (0, 0, 255), 2)
cv2.imshow("Rectangle", output)
cv2.waitKey(0)
</pre>

<p>First, we make a copy of the image on <strong>Line 75</strong> for reasons just explained.</p>
<p>Then we proceed to draw the rectangle.</p>
<p>Drawing rectangles in OpenCV couldn&#8217;t be any easier. Using pre-calculated coordinates, I&#8217;ve supplied the following parameters to the <code class="EnlighterJSRAW" data-enlighter-language="python">cv2.rectangle</code>  function on <strong>Line 76</strong>:</p>
<ul>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">img</code> : The destination image to draw upon. We&#8217;re drawing on <code class="EnlighterJSRAW" data-enlighter-language="python">output</code> .</li>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">pt1</code> : Our starting pixel coordinate which is the top-left. In our case, the top-left is <code class="EnlighterJSRAW" data-enlighter-language="python">(320, 60)</code> .</li>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">pt2</code> : The ending pixel &#8212; bottom-right. The bottom-right pixel is located at <code class="EnlighterJSRAW" data-enlighter-language="python">(420, 160)</code> .</li>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">color</code> : BGR tuple. To represent red, I&#8217;ve supplied <code class="EnlighterJSRAW" data-enlighter-language="python">(0 , 0, 255)</code> .</li>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">thickness</code> : Line thickness (a negative value will make a solid rectangle). I&#8217;ve supplied a thickness of <code class="EnlighterJSRAW" data-enlighter-language="python">2</code> .</li>
</ul>
<p>Since we are using OpenCV&#8217;s functions rather than NumPy operations we can supply our coordinates in <em>(x, y)</em> order rather than <em>(y, x)</em> since we are not manipulating or accessing the NumPy array directly &#8212; OpenCV is taking care of that for us.</p>
<p>Here&#8217;s our result in <strong>Figure 11</strong>:</p>
<figure id="attachment_7659" aria-describedby="caption-attachment-7659" style="width: 600px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_drawing_rectangle.jpg"><img class="size-full wp-image-7659" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_drawing_rectangle.jpg" alt="" width="600" height="375" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_drawing_rectangle.jpg 600w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_drawing_rectangle-300x188.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" /></a><figcaption id="caption-attachment-7659" class="wp-caption-text"><strong>Figure 11:</strong> Drawing shapes with OpenCV and Python is an easy skill to pick up. In this image, I&#8217;ve drawn a red box using <code>cv2.rectangle</code>. I pre-determined the coordinates around the face for this example, but you could use a face detection method to automatically find the face coordinates.</figcaption></figure>
<p>And now let&#8217;s place a solid blue circle in front of Dr. Ellie Sattler&#8217;s face:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="80" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="79">
# draw a blue 20px (filled in) circle on the image centered at
# x=300,y=150
output = image.copy()
cv2.circle(output, (300, 150), 20, (255, 0, 0), -1)
cv2.imshow("Circle", output)
cv2.waitKey(0)
</pre>

<p>To draw a circle, you need to supply following parameters to <code class="EnlighterJSRAW" data-enlighter-language="python">cv2.circle</code> :</p>
<ul>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">img</code> : The output image.</li>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">center</code> : Our circle&#8217;s center coordinate. I supplied <code class="EnlighterJSRAW" data-enlighter-language="python">(300, 150)</code>  which is right in front of Ellie&#8217;s eyes.</li>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">radius</code> : The circle radius in pixels. I provided a value of <code class="EnlighterJSRAW" data-enlighter-language="python">20</code>  pixels.</li>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">color</code> : Circle color. This time I went with blue as is denoted by 255 in the B and 0s in the G + R components of the BGR tuple, <code class="EnlighterJSRAW" data-enlighter-language="python">(255, 0, 0)</code> .</li>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">thickness</code> : The line thickness. Since I supplied a negative value (<code class="EnlighterJSRAW" data-enlighter-language="python">-1</code> ), the circle is solid/filled in.</li>
</ul>
<p>Here&#8217;s the result in <strong>Figure 12</strong>:</p>
<figure id="attachment_7660" aria-describedby="caption-attachment-7660" style="width: 600px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_drawing_circle.jpg"><img class="size-full wp-image-7660" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_drawing_circle.jpg" alt="" width="600" height="375" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_drawing_circle.jpg 600w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_drawing_circle-300x188.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" /></a><figcaption id="caption-attachment-7660" class="wp-caption-text"><strong>Figure 12:</strong> OpenCV&#8217;s <code>cv2.circle</code> method allows you to draw circles anywhere on an image. I&#8217;ve drawn a solid circle for this example as is denoted by the <code>-1</code> line thickness parameter (positive values will make a circular outline with variable line thickness).</figcaption></figure>
<p>It looks like Ellie is more interested in the dinosaurs than my big blue dot, so let&#8217;s move on!</p>
<p>Next, we&#8217;ll draw a red line. This line goes through Ellie&#8217;s head, past her eye, and to Ian&#8217;s hand.</p>
<p>If you look carefully at the method parameters and compare them to that of the rectangle, you&#8217;ll notice that they are identical:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="87" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="90">
# draw a 5px thick red line from x=60,y=20 to x=400,y=200
output = image.copy()
cv2.line(output, (60, 20), (400, 200), (0, 0, 255), 5)
cv2.imshow("Line", output)
cv2.waitKey(0)
</pre>

<p>Just as in a rectangle, we supply two points, a color, and a line thickness. OpenCV&#8217;s backend does the rest.</p>
<p><strong>Figure 13</strong> shows the result of <strong>Line 89</strong> from the code block:</p>
<figure id="attachment_7661" aria-describedby="caption-attachment-7661" style="width: 600px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_drawing_line.jpg"><img class="size-full wp-image-7661" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_drawing_line.jpg" alt="" width="600" height="375" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_drawing_line.jpg 600w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_drawing_line-300x188.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" /></a><figcaption id="caption-attachment-7661" class="wp-caption-text"><strong>Figure 13:</strong> Similar to drawing rectangles and circles, drawing a line in OpenCV using <code>cv2.line</code> only requires a starting point, ending point, color, and thickness.</figcaption></figure>
<p>Oftentimes you&#8217;ll find that you want to overlay text on an image for display purposes. If you&#8217;re working on face recognition you&#8217;ll likely want to draw the person&#8217;s name above their face. Or if you advance in your computer vision career you may build an image classifier or object detector. In these cases, you&#8217;ll find that you want to draw text containing the class name and probability.</p>
<p>Let&#8217;s see how OpenCV&#8217;s putText function works:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="93" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="91">
# draw green text on the image
output = image.copy()
cv2.putText(output, "OpenCV + Jurassic Park!!!", (10, 25), 
	cv2.FONT_HERSHEY_SIMPLEX, 0.7, (0, 255, 0), 2)
cv2.imshow("Text", output)
cv2.waitKey(0)
</pre>

<p>The <code class="EnlighterJSRAW" data-enlighter-language="python">putText</code>  function of OpenCV is responsible for drawing text on an image. Let&#8217;s take a look at the required parameters:</p>
<ul>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">img</code> : The output image.</li>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">text</code> : The string of text we&#8217;d like to write/draw on the image.</li>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">pt</code> : The starting point for the text.</li>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">font</code> : I often use the <code class="EnlighterJSRAW" data-enlighter-language="python">cv2.FONT_HERSHEY_SIMPLEX</code> . The available fonts are <a href="https://docs.opencv.org/3.4.1/d0/de1/group__core.html#ga0f9314ea6e35f99bb23f29567fc16e11" target="_blank" rel="noopener noreferrer">listed here</a>.</li>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">scale</code> : Font size multiplier.</li>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">color</code> : Text color.</li>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">thickness</code> : The thickness of the stroke in pixels.</li>
</ul>
<p>The code on <strong>Lines 95 and 96</strong> will draw the text, <em>&#8220;OpenCV + Jurassic Park!!!&#8221;</em> in green on our <code class="EnlighterJSRAW" data-enlighter-language="python">output</code>  image in <strong>Figure 14</strong>:</p>
<figure id="attachment_7662" aria-describedby="caption-attachment-7662" style="width: 600px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_drawing_text.jpg"><img class="size-full wp-image-7662" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_drawing_text.jpg" alt="" width="600" height="375" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_drawing_text.jpg 600w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_drawing_text-300x188.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" /></a><figcaption id="caption-attachment-7662" class="wp-caption-text"><strong>Figure 14:</strong> Oftentimes, you&#8217;ll find that you want to display text on an image for visualization purposes. Using the <code>cv2.putText</code> code shown above you can practice overlaying text on an image with different colors, fonts, sizes, and/or locations.</figcaption></figure>
<h3>Running the first OpenCV tutorial Python script</h3>
<p>In my blog posts, I generally provide a section detailing how you can run the code on your computer. At this point in the blog post, I make the following assumptions:</p>
<ol>
<li>You have downloaded the code from the <em><strong>&#8220;Downloads&#8221; </strong></em>section of this blog post.</li>
<li>You have unzipped the files.</li>
<li>You have installed OpenCV and the imutils library on your system.</li>
</ol>
<p>To execute our first script, open a terminal or command window and navigate to the files or extract them if necessary.</p>
<p>From there, enter the following command:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="shell" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="102">
$ python opencv_tutorial_01.py 
width=600, height=322, depth=3
R=41, G=49, B=37
</pre>

<p>The command is everything after the bash prompt <code class="EnlighterJSRAW" data-enlighter-language="shell">$</code>  character. Just type <code class="EnlighterJSRAW" data-enlighter-language="shell">python opencv_tutorial_01.py</code>  in your terminal and then the first image will appear.</p>
<p>To cycle through each step that we just learned, make sure an image window is active, and press any key.</p>
<p>Our first couple code blocks above told Python to print information in the terminal. If your terminal is visible, you&#8217;ll see the terminal output (<strong>Lines 2 and 3</strong>) shown.</p>
<p>I&#8217;ve also included a GIF animation demonstrating all the image processing steps we took sequentially, one right after the other:</p>
<figure id="attachment_7831" aria-describedby="caption-attachment-7831" style="width: 600px" class="wp-caption aligncenter"><img class="size-full wp-image-7831" src="https://pyimagesearch.com/wp-content/uploads/2018/06/opencv_tutorial_script_1_output.gif" alt="" width="600" height="500" /><figcaption id="caption-attachment-7831" class="wp-caption-text"><strong>Figure 15:</strong> Output animation displaying the OpenCV fundamentals we learned from this first example Python script.</figcaption></figure>
<h3>Counting objects</h3>
<p>Now we&#8217;re going to shift gears and work on the second script included in the <em><strong>&#8220;Downloads&#8221;</strong></em> associated with this blog post.</p>
<p>In the next few sections we&#8217;ll learn how to use create a simple Python + OpenCV script to count the number of Tetris blocks in the following image:</p>
<figure id="attachment_7663" aria-describedby="caption-attachment-7663" style="width: 482px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/tetris_blocks.png"><img class="size-full wp-image-7663" src="https://pyimagesearch.com/wp-content/uploads/2018/05/tetris_blocks.png" alt="" width="482" height="250" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/tetris_blocks.png 482w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/tetris_blocks-300x156.png 300w" sizes="(max-width: 482px) 100vw, 482px" /></a><figcaption id="caption-attachment-7663" class="wp-caption-text"><strong>Figure 16:</strong> If you&#8217;ve ever played Tetris (who hasn&#8217;t?), you&#8217;ll recognize these familiar shapes. In the 2nd half of this OpenCV fundamentals tutorial, we&#8217;re going to find and count the shape contours.</figcaption></figure>
<p>Along the way we&#8217;ll be:</p>
<ul>
<li>Learning how to convert images to grayscale with OpenCV</li>
<li>Performing edge detection</li>
<li>Thresholding a grayscale image</li>
<li>Finding, counting, and drawing contours</li>
<li>Conducting erosion and dilation</li>
<li>Masking an image</li>
</ul>
<p>Go ahead and close the first script you downloaded and open up <code class="EnlighterJSRAW" data-enlighter-language="shell">opencv_tutorial_02.py</code>  to get started with the second example:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="106">
# import the necessary packages
import argparse
import imutils
import cv2

# construct the argument parser and parse the arguments
ap = argparse.ArgumentParser()
ap.add_argument("-i", "--image", required=True,
	help="path to input image")
args = vars(ap.parse_args())
</pre>

<p>On <strong>Lines 2-4</strong> we import our packages. This is necessary at the start of each Python script. For this second script, I&#8217;ve imported <code class="EnlighterJSRAW" data-enlighter-language="python">argparse</code>  &#8212; a command line arguments parsing package which comes with all installations of Python.</p>
<p>Take a quick glance at <strong>Lines 7-10</strong>. These lines allow us to provide additional information to our program at runtime from within the terminal. Command line arguments are used heavily on the PyImageSearch blog and in all other computer science fields as well.</p>
<p><strong>I encourage you to read about them on this post: <em><a href="https://pyimagesearch.com/2018/03/12/python-argparse-command-line-arguments/" target="_blank" rel="noopener noreferrer">Python, argparse, and command line arguments</a>.</em></strong></p>
<p>We have one required command line argument <code class="EnlighterJSRAW" data-enlighter-language="python">--image</code>  , as is defined on <strong>Lines 8 and 9</strong>.</p>
<p>We&#8217;ll learn how to run the script with the required command line argument down below. For now, just know that wherever you encounter  <code class="EnlighterJSRAW" data-enlighter-language="python">args["image"]</code>  in the script, we&#8217;re referring to the path to the input image.</p>
<h3>Converting an image to grayscale</h3>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="12" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="110">
# load the input image (whose path was supplied via command line
# argument) and display the image to our screen
image = cv2.imread(args["image"])
cv2.imshow("Image", image)
cv2.waitKey(0)

# convert the image to grayscale
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
cv2.imshow("Gray", gray)
cv2.waitKey(0)
</pre>

<p>We load the image into memory on <strong>Line 14</strong>. The parameter to the <code class="EnlighterJSRAW" data-enlighter-language="python">cv2.imread</code>  function is our path contained in the <code class="EnlighterJSRAW" data-enlighter-language="python">args</code>  dictionary referenced with the <code class="EnlighterJSRAW" data-enlighter-language="python">"image"</code>  key, <code class="EnlighterJSRAW" data-enlighter-language="python">args["image"]</code> .</p>
<p>From there, we display the image until we encounter our first keypress (<strong>Lines 15 and 16</strong>).</p>
<p>We&#8217;re going to be thresholding and detecting edges in the image shortly. Therefore we convert the image to grayscale on <strong>Line 19</strong> by calling <code class="EnlighterJSRAW" data-enlighter-language="python">cv2.cvtColor</code>  and providing the <code class="EnlighterJSRAW" data-enlighter-language="python">image</code>  and <code class="EnlighterJSRAW" data-enlighter-language="python">cv2.COLOR_BGR2GRAY</code>  flag.</p>
<p>Again we display the image and wait for a keypress (<strong>Lines 20 and 21</strong>).</p>
<p>The result of our conversion to grayscale is shown in <strong>Figure 17</strong> (<em>bottom).</em></p>
<figure id="attachment_7664" aria-describedby="caption-attachment-7664" style="width: 450px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_grayscale.jpg"><img class="size-full wp-image-7664" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_grayscale.jpg" alt="" width="450" height="500" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_grayscale.jpg 450w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_grayscale-270x300.jpg 270w" sizes="(max-width: 450px) 100vw, 450px" /></a><figcaption id="caption-attachment-7664" class="wp-caption-text"><strong>Figure 17:</strong> (<em>top</em>) Our Tetris image. (<em>bottom</em>) We&#8217;ve converted the image to grayscale &#8212; a step that comes before thresholding.</figcaption></figure>
<h3>Edge detection</h3>
<p>Edge detection is useful for finding boundaries of objects in an image &#8212; it is effective for segmentation purposes.</p>
<p>Let&#8217;s perform edge detection to see how the process works:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="23" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="118">
# applying edge detection we can find the outlines of objects in
# images
edged = cv2.Canny(gray, 30, 150)
cv2.imshow("Edged", edged)
cv2.waitKey(0)
</pre>

<p>Using the popular Canny algorithm (developed by John F. Canny in 1986), we can find the edges in the image.</p>
<p>We provide three parameters to the <code class="EnlighterJSRAW" data-enlighter-language="python">cv2.Canny</code>  function:</p>
<ul>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">img</code> : The <code class="EnlighterJSRAW" data-enlighter-language="python">gray</code>  image.</li>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">minVal</code> : A minimum threshold, in our case <code class="EnlighterJSRAW" data-enlighter-language="python">30</code> .</li>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">maxVal</code> : The maximum threshold which is <code class="EnlighterJSRAW" data-enlighter-language="python">150</code>  in our example.</li>
<li><code class="EnlighterJSRAW" data-enlighter-language="python">aperture_size</code> : The Sobel kernel size. By default this value is <code class="EnlighterJSRAW" data-enlighter-language="python">3</code>  and hence is not shown on <strong>Line 25</strong>.</li>
</ul>
<p>Different values for the minimum and maximum thresholds will return different edge maps.</p>
<p>In <strong>Figure 18</strong> below, notice how edges of Tetris blocks themselves are revealed along with sub-blocks that make up the Tetris block:</p>
<figure id="attachment_7665" aria-describedby="caption-attachment-7665" style="width: 600px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_edge_detection.jpg"><img class="size-full wp-image-7665" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_edge_detection.jpg" alt="" width="600" height="377" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_edge_detection.jpg 600w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_edge_detection-300x189.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" /></a><figcaption id="caption-attachment-7665" class="wp-caption-text"><strong>Figure 18:</strong> To conduct edge detection with OpenCV, we make use of the Canny algorithm.</figcaption></figure>
<h3>Thresholding</h3>
<p>Image thresholding is an important intermediary step for image processing pipelines. Thresholding can help us to remove lighter or darker regions and contours of images.</p>
<p>I highly encourage you to experiment with thresholding. I tuned the following code to work for our example by trial and error (as well as experience):</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="29" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="128">
# threshold the image by setting all pixel values less than 225
# to 255 (white; foreground) and all pixel values &gt;= 225 to 255
# (black; background), thereby segmenting the image
thresh = cv2.threshold(gray, 225, 255, cv2.THRESH_BINARY_INV)[1]
cv2.imshow("Thresh", thresh)
cv2.waitKey(0)
</pre>

<p>In a single line (<strong>Line 32</strong>) we are:</p>
<ul>
<li>Grabbing all pixels in the <code class="EnlighterJSRAW" data-enlighter-language="python">gray</code>  image <em>greater than 225</em> and setting them to 0 (black) which corresponds to the <em>background</em> of the image</li>
<li>Setting pixel vales <em>less than 225</em> to 255 (white) which corresponds to the <em>foreground</em> of the image (i.e., the Tetris blocks themselves).</li>
</ul>
<p>For more information on the cv2.threshold function, including how the thresholding flags work, be sure to refer to <a href="https://docs.opencv.org/3.4.0/d7/d1b/group__imgproc__misc.html#ggaa9e58d2860d4afa658ef70a9b1115576a19120b1a11d8067576cc24f4d2f03754" target="_blank" rel="noopener noreferrer">official OpenCV documentation</a>.</p>
<p>Segmenting foreground from background with a binary image is <em><strong>critical</strong></em> to finding contours (our next step).</p>
<figure id="attachment_7666" aria-describedby="caption-attachment-7666" style="width: 600px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_thresholding.png"><img class="size-full wp-image-7666" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_thresholding.png" alt="" width="600" height="377" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_thresholding.png 600w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_thresholding-300x189.png 300w" sizes="(max-width: 600px) 100vw, 600px" /></a><figcaption id="caption-attachment-7666" class="wp-caption-text"><strong>Figure 19:</strong> Prior to finding contours, we threshold the grayscale image. We performed a binary inverse threshold so that the foreground shapes become white while the background becomes black.</figcaption></figure>
<p>Notice in <strong>Figure 19</strong> that the foreground objects are white and the background is black.</p>
<h3>Detecting and drawing contours</h3>
<figure id="attachment_7667" aria-describedby="caption-attachment-7667" style="width: 500px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_contours_animation.gif"><img class="wp-image-7667 size-full" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_contours_animation.gif" alt="" width="500" height="314" /></a><figcaption id="caption-attachment-7667" class="wp-caption-text"><strong>Figure 20:</strong> We&#8217;re working towards finding contour shapes with OpenCV and Python in this OpenCV Basics tutorial.</figcaption></figure>
<p>Pictured in the <strong>Figure 20</strong> animation, we have 6 shape contours. Let&#8217;s find and draw their outlines via code:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="36" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="130">
# find contours (i.e., outlines) of the foreground objects in the
# thresholded image
cnts = cv2.findContours(thresh.copy(), cv2.RETR_EXTERNAL,
	cv2.CHAIN_APPROX_SIMPLE)
cnts = imutils.grab_contours(cnts)
output = image.copy()

# loop over the contours
for c in cnts:
	# draw each contour on the output image with a 3px thick purple
	# outline, then display the output contours one at a time
	cv2.drawContours(output, [c], -1, (240, 0, 159), 3)
	cv2.imshow("Contours", output)
	cv2.waitKey(0)
</pre>

<p>On <strong>Lines 38 and 39</strong>, we use <code class="EnlighterJSRAW" data-enlighter-language="python">cv2.findContours</code>  to detect the contours in the image. Take note of the parameter flags but for now let&#8217;s keep things simple &#8212; our algorithm is finding all foreground (white) pixels in the <code class="EnlighterJSRAW" data-enlighter-language="python">thresh.copy()</code>  image.</p>
<p><strong>Line 40</strong> is very important accounting for the fact that <code class="EnlighterJSRAW" data-enlighter-language="python">cv2.findContours</code>  implementation changed between OpenCV 2.4, OpenCV 3, and OpenCV 4. This compatibility line is present on the blog wherever contours are involved.</p>
<p>We make a copy of the original image on <strong>Line 41</strong> so that we can draw contours on subsequent <strong>Lines 44-49</strong>.</p>
<p>On <strong>Line 47</strong> we draw each <code class="EnlighterJSRAW" data-enlighter-language="python">c</code>  from the <code class="EnlighterJSRAW" data-enlighter-language="python">cnts</code>  list on the image using the appropriately named <code class="EnlighterJSRAW" data-enlighter-language="python">cv2.drawContours</code> . I chose purple which is represented by the tuple <code class="EnlighterJSRAW" data-enlighter-language="python">(240, 0, 159)</code> .</p>
<p>Using what we learned earlier in this blog post, let&#8217;s overlay some text on the image:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="51" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="138">
# draw the total number of contours found in purple
text = "I found {} objects!".format(len(cnts))
cv2.putText(output, text, (10, 25),  cv2.FONT_HERSHEY_SIMPLEX, 0.7,
	(240, 0, 159), 2)
cv2.imshow("Contours", output)
cv2.waitKey(0)
</pre>

<p><strong>Line 52</strong> builds a <code class="EnlighterJSRAW" data-enlighter-language="python">text</code>  string containing the number of shape contours. Counting the total number of objects in this image is as simple as checking the length of the contours list &#8212; <code class="EnlighterJSRAW" data-enlighter-language="python">len(cnts)</code> .</p>
<p>The result is shown in <strong>Figure 21</strong>:</p>
<figure id="attachment_7669" aria-describedby="caption-attachment-7669" style="width: 600px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_object_counting.jpg"><img class="size-full wp-image-7669" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_object_counting.jpg" alt="" width="600" height="377" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_object_counting.jpg 600w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_object_counting-300x189.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" /></a><figcaption id="caption-attachment-7669" class="wp-caption-text"><strong>Figure 21:</strong> Counting contours with OpenCV is as easy as finding them and then calling <code>len(cnts)</code>.</figcaption></figure>
<h3>Erosions and dilations</h3>
<p>Erosions and dilations are typically used to reduce noise in binary images (a side effect of thresholding).</p>
<p>To reduce the size of foreground objects we can erode away pixels given a number of iterations:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="58" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="141">
# we apply erosions to reduce the size of foreground objects
mask = thresh.copy()
mask = cv2.erode(mask, None, iterations=5)
cv2.imshow("Eroded", mask)
cv2.waitKey(0)
</pre>

<p>On <strong>Line 59</strong> we copy the <code class="EnlighterJSRAW" data-enlighter-language="python">thresh</code>  image while naming it <code class="EnlighterJSRAW" data-enlighter-language="python">mask</code> .</p>
<p>Then, utilizing <code class="EnlighterJSRAW" data-enlighter-language="python">cv2.erode</code> , we proceed to reduce the contour sizes with 5 <code class="EnlighterJSRAW" data-enlighter-language="python">iterations</code>  (<strong>Line 60</strong>).</p>
<p>Demonstrated in <strong>Figure 22</strong>, the masks generated from the Tetris contours are slightly smaller:</p>
<figure id="attachment_7670" aria-describedby="caption-attachment-7670" style="width: 600px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_erosion.jpg"><img class="size-full wp-image-7670" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_erosion.jpg" alt="" width="600" height="377" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_erosion.jpg 600w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_erosion-300x189.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" /></a><figcaption id="caption-attachment-7670" class="wp-caption-text"><strong>Figure 22:</strong> Using OpenCV we can erode contours, effectively making them smaller or causing them to disappear completely with sufficient iterations. This is typically useful for removing small blobs in mask image.</figcaption></figure>
<p>Similarly, we can foreground regions in the mask. To enlarge the regions, simply use <code class="EnlighterJSRAW" data-enlighter-language="python">cv2.dilate</code> :</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="64" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="147">
# similarly, dilations can increase the size of the ground objects
mask = thresh.copy()
mask = cv2.dilate(mask, None, iterations=5)
cv2.imshow("Dilated", mask)
cv2.waitKey(0)
</pre>

<figure id="attachment_7671" aria-describedby="caption-attachment-7671" style="width: 600px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_dilation.jpg"><img class="wp-image-7671 size-full" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_dilation.jpg" alt="" width="600" height="377" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_dilation.jpg 600w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_dilation-300x189.jpg 300w" sizes="(max-width: 600px) 100vw, 600px" /></a><figcaption id="caption-attachment-7671" class="wp-caption-text"><strong>Figure 23:</strong> In an image processing pipeline if you ever have the need to connect nearby contours, you can apply dilation to the image. Shown in the figure is the result of dilating contours with five iterations, but not to the point of two contours becoming one.</figcaption></figure>
<h3>Masking and bitwise operations</h3>
<p>Masks allow us to &#8220;mask out&#8221; regions of an image we are uninterested in. We call them &#8220;masks&#8221; because they will <em>hide</em> regions of images we do not care about.</p>
<p>If we use the thresh image from <strong>Figure 18</strong> and mask it with the original image, we&#8217;re presented with <strong>Figure 23</strong>:</p>
<figure id="attachment_7673" aria-describedby="caption-attachment-7673" style="width: 600px" class="wp-caption aligncenter"><a href="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_bitwise_masking.jpg"><img class="wp-image-7673" src="https://pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_bitwise_masking.jpg" alt="" width="600" height="377" srcset="https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_bitwise_masking.jpg 1000w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_bitwise_masking-300x189.jpg 300w, https://www.pyimagesearch.com/wp-content/uploads/2018/05/opencv_tutorial_bitwise_masking-768x483.jpg 768w" sizes="(max-width: 600px) 100vw, 600px" /></a><figcaption id="caption-attachment-7673" class="wp-caption-text"><strong>Figure 24:</strong> When using the thresholded image as the mask in comparison to our original image, the colored regions reappear as the rest of the image is &#8220;masked out&#8221;. This is, of course, a simple example, but as you can imagine, masks are very powerful.</figcaption></figure>
<p>In <strong>Figure 24</strong>, the background is black now and our foreground consists of colored pixels &#8212; any pixels masked by our <code class="EnlighterJSRAW" data-enlighter-language="python">mask</code>  image.</p>
<p>Let&#8217;s learn how to accomplish this:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="python" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="70" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="149">
# a typical operation we may want to apply is to take our mask and
# apply a bitwise AND to our input image, keeping only the masked
# regions
mask = thresh.copy()
output = cv2.bitwise_and(image, image, mask=mask)
cv2.imshow("Output", output)
cv2.waitKey(0)
</pre>

<p>The <code class="EnlighterJSRAW" data-enlighter-language="python">mask</code>  is generated by copying the binary <code class="EnlighterJSRAW" data-enlighter-language="python">thresh</code>  image (<strong>Line 73</strong>).</p>
<p>From there we bitwise AND the pixels from both images together using <code class="EnlighterJSRAW" data-enlighter-language="python">cv2.bitwise_and</code> .</p>
<p>The result is <strong>Figure 24</strong> above where now we&#8217;re only showing/highlighting the Tetris blocks.</p>
<h3>Running the second OpenCV tutorial Python script</h3>
<p>To run the second script, be sure you&#8217;re in the folder containing your downloaded source code and Python scripts. From there, we&#8217;ll open up a terminal provide the script name + <a href="https://pyimagesearch.com/2018/03/12/python-argparse-command-line-arguments/" target="_blank" rel="noopener noreferrer">command line argument</a>:</p>

<pre class="EnlighterJSRAW" data-enlighter-language="shell" data-enlighter-theme="" data-enlighter-highlight="" data-enlighter-linenumbers="true" data-enlighter-lineoffset="" data-enlighter-title="OpenCV Tutorial: A Guide to Learn OpenCV" data-enlighter-group="153">
$ python opencv_tutorial_02.py --image tetris_blocks.png
</pre>

<p>The argument flag is <code class="EnlighterJSRAW" data-enlighter-language="python">--image</code>  and the image argument itself is <code class="EnlighterJSRAW" data-enlighter-language="shell">tetris_blocks.png</code>  &#8212; a path to the relevant file in the directory.</p>
<p>There is no terminal output for this script. Again, to cycle through the images, be sure you click on an image window to make it active, from there you can press a key and it will be captured to move forward to the next <code class="EnlighterJSRAW" data-enlighter-language="python">waitKey(0)</code>  in the script. When the program is finished running, your script will exit gracefully and you&#8217;ll be presented with a new bash prompt line in your terminal.</p>
<p>Below I have included a GIF animation of the basic OpenCV image processing steps in our example script:</p>
<figure id="attachment_7832" aria-describedby="caption-attachment-7832" style="width: 600px" class="wp-caption aligncenter"><img class="size-full wp-image-7832" src="https://pyimagesearch.com/wp-content/uploads/2018/06/opencv_tutorial_script_2_output.gif" alt="" width="600" height="500" /><figcaption id="caption-attachment-7832" class="wp-caption-text"><strong>Figure 25:</strong> Learning OpenCV and the basics of computer vision by counting objects via contours.</figcaption></figure>
<h2>Where can I learn more?</h2>
<p><a href="https://pyimagesearch.com/practical-python-opencv/" target="_blank" rel="noopener noreferrer"><img class="aligncenter wp-image-4636 size-full" src="https://pyimagesearch.com/wp-content/uploads/2016/09/curious_about_cv.jpg" alt="" width="400" height="400" srcset="https://www.pyimagesearch.com/wp-content/uploads/2016/09/curious_about_cv.jpg 400w, https://www.pyimagesearch.com/wp-content/uploads/2016/09/curious_about_cv-150x150.jpg 150w, https://www.pyimagesearch.com/wp-content/uploads/2016/09/curious_about_cv-300x300.jpg 300w" sizes="(max-width: 400px) 100vw, 400px" /></a></p>
<p>If you’re looking to continue learning OpenCV and computer vision, be sure to take a look at my book, <em><a href="https://pyimagesearch.com/practical-python-opencv/" target="_blank" rel="noopener noreferrer">Practical Python and OpenCV</a>.</em></p>
<p>Inside the book we’ll explore the OpenCV fundamentals we discussed here today in more detail.</p>
<p><strong>You’ll also learn how to use these fundamentals to build actual computer vision + OpenCV applications, including:</strong></p>
<ul>
<li>Face detection in images and video</li>
<li>Handwriting recognition</li>
<li>Feature extraction and machine learning</li>
<li>Basic object tracking</li>
<li><em>&#8230;and more!</em></li>
</ul>
<p>To learn more about <em>Practical Python and OpenCV</em>, and how it can help you learn OpenCV (in less than a single weekend), <a href="https://pyimagesearch.com/practical-python-opencv/" target="_blank" rel="noopener noreferrer"><em><strong>just click here.</strong></em></a></p>
<h2>Summary</h2>
<p>In today’s blog post you learned the fundamentals of image processing and OpenCV using the Python programming language.</p>
<p>You are now prepared to start using these image processing operations as “building blocks” you can chain together to build an actual computer vision application — a great example of such a project is the basic object counter we created by counting contours.</p>
<p>I hope this tutorial helped you learn OpenCV!</p>
<p><strong>To be notified when future OpenCV blog posts are published here on PyImageSearch, <em>just enter your email address in the form below!</em></strong></p>
<div id="download-the-code" class="post-cta-wrap">
<div class="gpd-post-cta">
	<div class="gpd-post-cta-content">
		

			<div class="gpd-post-cta-top">
				<div class="gpd-post-cta-top-image"><img src="https://www.pyimagesearch.com/wp-content/uploads/2020/01/cta-source-guide-1.png" alt="" /></div>
				
				<div class="gpd-post-cta-top-title"><h4>Download the Source Code and FREE 17-page Resource Guide</h4></div>
				<div class="gpd-post-cta-top-desc"><p>Enter your email address below to get a .zip of the code and a <strong>FREE 17-page Resource Guide on Computer Vision, OpenCV, and Deep Learning.</strong> Inside you’ll find my hand-picked tutorials, books, courses, and libraries to help you master CV and DL!</p></div>


			</div>

			<div class="gpd-post-cta-bottom">
				<form class="footer-cta" action="https://www.getdrip.com/forms/878670517/submissions" method="post" target="blank" data-drip-embedded-form="878670517">
					<input name="fields[email]" type="email" value="" placeholder="Your email address" class="form-control" />

					<button type="submit">Download the code!</button>

					<div style="display: none;" aria-hidden="true"><label for="website">Website</label><br /><input type="text" id="website" name="website" tabindex="-1" autocomplete="false" value="" /></div>
				</form>
			</div>


		
	</div>

</div>
</div>
<!-- RightMessage WP -->
<script type="text/javascript">
		window.rmpanda = window.rmpanda || {};
	window.rmpanda.cmsdata = {"cms":"wordpress","postId":7642,"taxonomyTerms":{"category":[572,27],"post_tag":[469,80,106,75,76,4,15,17,164],"post_format":[]}};
	</script><!--<rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
			xmlns:dc="http://purl.org/dc/elements/1.1/"
			xmlns:trackback="http://madskills.com/public/xml/rss/module/trackback/">
		<rdf:Description rdf:about="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/"
    dc:identifier="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/"
    dc:title="OpenCV Tutorial: A Guide to Learn OpenCV"
    trackback:ping="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/trackback/" />
</rdf:RDF>-->
</div></article><section class="author-box"><img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=240&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=480&#038;d=mm&#038;r=g 2x' class='avatar avatar-240 photo' height='240' width='240' /><h4 class="author-box-title"><strong>About the Author</strong></h4><div class="author-box-content" itemprop="description"><p>Hi there, I’m Adrian Rosebrock, PhD. All too often I see developers, students, and researchers wasting their time, studying the wrong things, and generally struggling to get started with Computer Vision, Deep Learning, and OpenCV. I created this website to show you what I believe is the best possible way to get your start.</p>
</div></section><h2 class="screen-reader-text">Reader Interactions</h2><div class="single-post-nav"><a href="https://www.pyimagesearch.com/2018/07/16/opencv-saliency-detection/"><div class="single-post-nav__previous"><p>Previous Article:</p><h3>OpenCV Saliency Detection</h3></div></a><a href="https://www.pyimagesearch.com/2018/07/23/simple-object-tracking-with-opencv/"><div class="single-post-nav__next"><p>Next Article:</p><h3>Simple object tracking with OpenCV</h3></div></a></div><div class="entry-comments" id="comments"><h3>79 responses to: OpenCV Tutorial: A Guide to Learn OpenCV</h3><ol class="comment-list">
	<li class="comment even thread-even depth-1" id="comment-471468">
	<article id="article-comment-471468">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/d6daefe32d86a7eb16a39c0f1338a50f?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/d6daefe32d86a7eb16a39c0f1338a50f?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Hacklavya</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-471468">July 19, 2018 at 4:13 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Why don&#8217;t you switch to conda environment, that is much easy to deal with than this virtualenv and virtualenvwrapper.</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor odd alt depth-2" id="comment-471518">
	<article id="article-comment-471518">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-471518">July 20, 2018 at 6:28 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Yes and no. Conda has positives but it can also be restrictive. Conda has the benefit of having OpenCV ready to go, but there&#8217;s no guarantee it&#8217;s been optimized for your particular build either. I also have zero intention on forcing people to use one environment over another &#8212; use whatever you are comfortable with, but I do recommend Python virtual environments in some form, regardless if you&#8217;re using Conda or virtualenv/virtualenvwrapper.</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment even depth-3" id="comment-471564">
	<article id="article-comment-471564">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/d6daefe32d86a7eb16a39c0f1338a50f?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/d6daefe32d86a7eb16a39c0f1338a50f?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Hacklavya</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-471564">July 20, 2018 at 11:05 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Thanks Adrian</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-odd thread-alt depth-1" id="comment-471553">
	<article id="article-comment-471553">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/41bef5cba1ee0c948e2342ecd63d7dfe?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/41bef5cba1ee0c948e2342ecd63d7dfe?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">masefc11</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-471553">July 20, 2018 at 7:50 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>How to install latest pakages of opencv python like 3.4.2 which isn&#8217;t available yet with pip command.</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-471629">
	<article id="article-comment-471629">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-471629">July 21, 2018 at 7:38 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>You&#8217;ll want to follow <a target="blank" href="https://www.pyimagesearch.com/opencv-tutorials-resources-guides/">one of my tutorials</a> and compile from source.</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->

	<li class="comment odd alt depth-2" id="comment-510459">
	<article id="article-comment-510459">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/7814fce8e88792c2a1f439bec4127404?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/7814fce8e88792c2a1f439bec4127404?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name"><a href="http://www.imanssoftware.com" class="comment-author-link" rel="external nofollow">Vijay Balkrishna Konduskar</a></span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-510459">April 1, 2019 at 3:51 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>just open command prompt with admin rights and type following command </p>
<p>python -m pip install opencv-python</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-3" id="comment-510574">
	<article id="article-comment-510574">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-510574">April 2, 2019 at 5:47 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>I would recommend using &#8220;opencv-contrib-python&#8221; instead. Anyone trying to install OpenCV via pip should read <a target="blank" href="https://www.pyimagesearch.com/2018/09/19/pip-install-opencv/">this post first.</a></p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-even depth-1" id="comment-471568">
	<article id="article-comment-471568">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/f69823e3d6b71babf9a5347f309a5631?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/f69823e3d6b71babf9a5347f309a5631?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">h3a</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-471568">July 20, 2018 at 12:09 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Hi Adrian!</p>
<p>At the start of the post you say : &#8220;OpenCV Project Structure<br />
Before going too far down the rabbit hole, be sure to grab the code + images from the “Downloads” section of today’s blog post.&#8221;</p>
<p>In the downloads section there is only your Resource Guide&#8230;</p>
<p>Thanks for everything,<br />
h3a</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-471628">
	<article id="article-comment-471628">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-471628">July 21, 2018 at 7:38 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Directly underneath the &#8220;Downloads&#8221; header there is a form with a button that says &#8220;Download the Code!&#8221;. I think you may have missed that form.</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-odd thread-alt depth-1" id="comment-475227">
	<article id="article-comment-475227">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/c5a614c796d471aea6466b4e6502813a?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/c5a614c796d471aea6466b4e6502813a?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name"><a href="http://this-mysterious-world.blogspot.com" class="comment-author-link" rel="external nofollow">Luis M</a></span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-475227">August 22, 2018 at 7:37 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>This is an excellent course of OpenCV, just what I needed! Thanks!</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-475405">
	<article id="article-comment-475405">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-475405">August 24, 2018 at 8:47 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Thanks Luis, I&#8217;m glad it helped you! 🙂</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-even depth-1" id="comment-477929">
	<article id="article-comment-477929">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/dd13cbf1b8b3659152073e0e792e73e9?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/dd13cbf1b8b3659152073e0e792e73e9?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Parth Agarwal</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-477929">September 13, 2018 at 4:35 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Great tutorial Adrian, this got me started with OpenCV. I think there&#8217;s a mistake in the angle mentioned for bounded rotation in the Jurassic Park:</p>
<p># OpenCV doesn&#8217;t &#8220;care&#8221; if our rotated image is clipped after rotation<br />
# so we can instead use another imutils convenience function to help<br />
# us out<br />
rotated = imutils.rotate_bound(image, 45)<br />
cv2.imshow(&#8220;Imutils Bound Rotation&#8221;, rotated)<br />
cv2.waitKey(0)</p>
<p>Here the angle should be -45 instead of +45 if I am correct.</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-478072">
	<article id="article-comment-478072">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-478072">September 14, 2018 at 9:26 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>The <a target="blank" href="https://github.com/jrosebr1/imutils/blob/master/imutils/convenience.py#L50" rel="nofollow">rotate_bound function</a> actually takes the negative of the angle so the code is correct.</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment odd alt depth-3" id="comment-478204">
	<article id="article-comment-478204">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/dd13cbf1b8b3659152073e0e792e73e9?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/dd13cbf1b8b3659152073e0e792e73e9?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Parth Agarwal</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-478204">September 15, 2018 at 1:15 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>OK, got it, thanks.</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment even thread-odd thread-alt depth-1" id="comment-480977">
	<article id="article-comment-480977">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/de24cdc9e3d3cbdd2b6325b7ccb185cd?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/de24cdc9e3d3cbdd2b6325b7ccb185cd?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">shiva kumar</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-480977">October 6, 2018 at 7:25 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>When i ran tutorial_02.py i got the below error. Pl help.</p>
<p>usage: opencv_tutorial_02.py [-h] -i IMAGE<br />
opencv_tutorial_02.py: error: the following arguments are required: -i/&#8211;image<br />
An exception has occurred, use %tb to see the full traceback.</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor odd alt depth-2" id="comment-481166">
	<article id="article-comment-481166">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-481166">October 8, 2018 at 9:40 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>It sounds like you are trying to execute the script within IPython. Instead, execute it via command line argument and <a target="blank" href="https://www.pyimagesearch.com/2018/03/12/python-argparse-command-line-arguments/">supply the command line arguments.</a></p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment even thread-even depth-1" id="comment-483072">
	<article id="article-comment-483072">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/344ff1d81f468dbe5a03dd72f0db908c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/344ff1d81f468dbe5a03dd72f0db908c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">shincheng</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-483072">October 18, 2018 at 4:28 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>A 640 x 480 image has 640 rows and 480 columns.<br />
Should it be 480 rows and 640 columns???</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor odd alt depth-2" id="comment-483305">
	<article id="article-comment-483305">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-483305">October 20, 2018 at 7:43 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Yes, thank you for catching this typo! I have updated the blog post 🙂 Thanks again!</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment even thread-odd thread-alt depth-1" id="comment-483463">
	<article id="article-comment-483463">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/addb48026292141d5f5e785034103765?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/addb48026292141d5f5e785034103765?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Vishal</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-483463">October 21, 2018 at 2:14 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>In the Masking and bitwise operations sections why do we use image twice in </p>
<p>cv2.bitwise_and(image,image,mask) ?</p>
<p>What is the differece between using the same image twice and suing two diff images?</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor odd alt depth-2" id="comment-483549">
	<article id="article-comment-483549">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-483549">October 22, 2018 at 7:56 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>We need two inputs to perform bitwise ANDs and ORs. Since our goal is applying the mask to the image we supply the input image twice as both inputs so the output will always be TRUE expect for where the mask is applied.</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment even thread-even depth-1" id="comment-483933">
	<article id="article-comment-483933">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/fd42b0fe075f9cb1665280983c27af86?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/fd42b0fe075f9cb1665280983c27af86?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Phong</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-483933">October 25, 2018 at 1:49 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>I can&#8217;t execute your code to the your images. I coppied all the code you write but the images stay the same before processed. Is there any problems like outdated OpenCV lib version or something else?</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor odd alt depth-2" id="comment-484478">
	<article id="article-comment-484478">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-484478">October 29, 2018 at 1:51 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>I don&#8217;t suggest copying and pasting. Make sure you use the &#8220;Downloads&#8221; section of the blog post to download the code and example images. From there you can run the script. My guess is that you accidentally introduced an error in the code or logic during the copy and paste.</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment even thread-odd thread-alt depth-1" id="comment-485887">
	<article id="article-comment-485887">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/f0eef4526e3a96b7a5e1f569d886ea7f?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/f0eef4526e3a96b7a5e1f569d886ea7f?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Joel</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-485887">November 7, 2018 at 1:32 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>cnts = cnts[0] if imutils.is_cv2() else cnts[1]</p>
<p>How the array stores more than one element? Like cnts[0], cnts[1], cnts[2]&#8230;..</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->

	<li class="comment odd alt thread-even depth-1" id="comment-492247">
	<article id="article-comment-492247">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/d1a2cfeb817c14e17cba57b02ddaeb55?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/d1a2cfeb817c14e17cba57b02ddaeb55?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Agribot</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-492247">December 14, 2018 at 12:03 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Hi,<br />
Thanks for posting this helpful article, code and details of how-to.</p>
<p>I&#8217;m a newbe to the area of python + computer vision + opencv, so I bought one of your bundles listed at;-<br />
<a href="https://www.pyimagesearch.com/practical-python-opencv/" rel="nofollow ugc">https://www.pyimagesearch.com/practical-python-opencv/</a></p>
<p>and I found the information and examples very helpful as i struggled to get my head around some topics. It was very useful to have the bundle available, </p>
<p>Better than searching around to pull together pieces of information and / or python examples<br />
The bundle gave it all together &#8211; at a good level of clarity.</p>
<p>keep up the good work.</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-492840">
	<article id="article-comment-492840">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-492840">December 18, 2018 at 9:22 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Thank you so much for picking up a copy, Agribot! I&#8217;m so happy to hear you found the book helpful. Enjoy it!</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-odd thread-alt depth-1" id="comment-497290">
	<article id="article-comment-497290">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/9217031e2e77508c75ee62b3801d9287?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/9217031e2e77508c75ee62b3801d9287?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Priyanka Saggu</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-497290">January 21, 2019 at 12:36 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Hi Adrian,</p>
<p>So, grateful for all your useful and rich content. I want to know:<br />
1. what changes are meant to be made if the background is any color other than white?<br />
2. How to get rid of the coinciding shadows of different objects. As 2 objects with intersecting shadows are counted as 1?</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-497423">
	<article id="article-comment-497423">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-497423">January 22, 2019 at 9:17 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>1. Which image are you referring to?</p>
<p>2. Use the <a target="blank" href="https://www.pyimagesearch.com/2015/11/02/watershed-opencv/">Watershed algorithm.</a></p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment odd alt depth-3" id="comment-497502">
	<article id="article-comment-497502">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/9217031e2e77508c75ee62b3801d9287?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/9217031e2e77508c75ee62b3801d9287?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Priyanka Saggu</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-497502">January 22, 2019 at 12:26 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>I meant to ask, that the images which are taken as an example while counting the no. of objects, has a white background. So, what if an image has a background color other than white. What changes should be made in that case?</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-4" id="comment-497878">
	<article id="article-comment-497878">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-497878">January 25, 2019 at 7:47 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>You could either:</p>
<p>1. Invert the image via <code>cv2.bitwise_not</code><br />
2. Swap the flag to <code>cv2.THRESH_BINARY</code> when thresholding</p>
<p>For more information on the basics of computer vision and image processing I would definitely suggest referring to <a target="blank" href="https://www.pyimagesearch.com/practical-python-opencv/">Practical Python and OpenCV</a> which covers them in detail.</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-even depth-1" id="comment-501255">
	<article id="article-comment-501255">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/b1e14029988e57a757adfb615c7d42aa?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/b1e14029988e57a757adfb615c7d42aa?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Tehreem Qasim</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-501255">February 14, 2019 at 8:08 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Dear Adrian,<br />
I get the following error,</p>
<p>module &#8216;imutils&#8217; has no attribute &#8216;grabcontours&#8217;.</p>
<p>Some one else has raised the same concern here:<br />
<a href="https://python-forum.io/Thread-imutils-grab-contours-error-reg" rel="nofollow ugc">https://python-forum.io/Thread-imutils-grab-contours-error-reg</a></p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-501289">
	<article id="article-comment-501289">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-501289">February 14, 2019 at 12:44 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>You simply need to upgrade your imutils install:</p>
<p><code>$ pip install --upgrade imutils</code></p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-odd thread-alt depth-1" id="comment-501926">
	<article id="article-comment-501926">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/65e635fa7bb3abaf248b06ce3904703b?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/65e635fa7bb3abaf248b06ce3904703b?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Mohammed Patel</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-501926">February 17, 2019 at 7:03 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Hi! I have learnt a lot from this tutorial! I was wondering how I could count objects for images with slightly shaded backgrounds with shadows and without knowing the highest shadow value to threshold from. Please can you help me with this?</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-502524">
	<article id="article-comment-502524">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-502524">February 20, 2019 at 12:36 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Take a look into &#8220;adaptive thresholding&#8221; methods. I cover them inside <a target="blank" href="https://www.pyimagesearch.com/practical-python-opencv/">Practical Python and OpenCV.</a></p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-even depth-1" id="comment-505211">
	<article id="article-comment-505211">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/f5483e1a7e3d190cbce965dc83b1fbd0?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/f5483e1a7e3d190cbce965dc83b1fbd0?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Aishvarya Kumar Jain</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-505211">March 6, 2019 at 4:42 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Hi&#8230;thanks for building up this wonderful course. I am bit curious about the function rotate_bounded() and rotate().</p>
<p>Why there is non uniformity between the function when passing the angle of rotation?<br />
rotate() consider negative angles as clockwise but rotate_bounded() consider positive angles as clockwise.</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-505587">
	<article id="article-comment-505587">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-505587">March 8, 2019 at 5:46 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>It was simply how I implemented the &#8220;rotate_bounded&#8221; function, that&#8217;s all.</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-odd thread-alt depth-1" id="comment-508689">
	<article id="article-comment-508689">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/840af38ab6f385c684ba6cb439a60276?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/840af38ab6f385c684ba6cb439a60276?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Devansh Shah</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-508689">March 23, 2019 at 2:23 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Hey! I have downloaded the tutorial file and when I run the code &#8220;opencv_tutorial_01.py&#8221;, everything seems to be working fine, i.e the size of the image outputted is right, the pixel value for the specific pixel chosen is right according to the blog, however: all the images in my display window just appear white. I am using Mac OSx btw, thanks</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-509467">
	<article id="article-comment-509467">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-509467">March 27, 2019 at 9:23 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>That&#8217;s definitely very strange. How did you install OpenCV on your machine? Did you follow one of my tutorials?</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment odd alt depth-3" id="comment-513787">
	<article id="article-comment-513787">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/e2e24f9a40d1d6258e8a5692b9918a40?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/e2e24f9a40d1d6258e8a5692b9918a40?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Ramisha</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-513787">April 20, 2019 at 9:38 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Thank you for your tutorial.</p>
<p>What is the math behind converting a grayscale image to color image?</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-4" id="comment-514731">
	<article id="article-comment-514731">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-514731">April 25, 2019 at 9:19 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Hey Ramisha &#8212; I noticed you posted a few comments across various posts on the PyImageSearch blog. It&#8217;s great that you&#8217;re enjoying the tutorials but I would recommend you read through <a target="blank" href="https://www.pyimagesearch.com/practical-python-opencv/">Practical Python and OpenCV</a> &#8212; that book will teach you the basics.</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-even depth-1" id="comment-520626">
	<article id="article-comment-520626">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/f242d3abfd5e79dc60afa55b22cc9c3f?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/f242d3abfd5e79dc60afa55b22cc9c3f?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Ettienne Gerwel</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-520626">June 3, 2019 at 10:00 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Great tutorial!!!!! Well done!</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-521020">
	<article id="article-comment-521020">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-521020">June 6, 2019 at 7:58 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Thanks so much, I&#8217;m glad you liked it!</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-odd thread-alt depth-1" id="comment-522195">
	<article id="article-comment-522195">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/becc278c23f71e6df8a653fc845b0b46?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/becc278c23f71e6df8a653fc845b0b46?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name"><a href="http://pyimagesearch.com" class="comment-author-link" rel="external nofollow">sonny osunkwo</a></span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-522195">June 18, 2019 at 11:12 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>why is this course not designed for windows OS?</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-522312">
	<article id="article-comment-522312">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-522312">June 19, 2019 at 1:46 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>The code will work on Windows, I just do not support Windows on the PyImageSearch blog. See <a target="blank" href="https://www.pyimagesearch.com/faqs/single-faq/can-you-help-me-do-___-on-windows">this link.</a></p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-even depth-1" id="comment-522634">
	<article id="article-comment-522634">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/04e5f5e8dbfd7c5b8c529a99bd3caa88?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/04e5f5e8dbfd7c5b8c529a99bd3caa88?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Zlatko</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-522634">June 22, 2019 at 12:45 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Hello again!</p>
<p>I asked for help yesterday, but I need not it any more. I have found mistake: in code I received there was statement: </p>
<p>                       image = cv2.imread(&#8220;tetris_blocks&#8221;)</p>
<p>instead of: </p>
<p>                       image = cv2.imread(&#8220;tetris_blocks.png&#8221;)</p>
<p>Regardless, thank you very much for your efforts and good will in helping me to learn basics of Computer vision and image processing!</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-523172">
	<article id="article-comment-523172">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-523172">June 26, 2019 at 1:37 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Yes, always make sure to double and triple-check those files paths 🙂</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-odd thread-alt depth-1" id="comment-524148">
	<article id="article-comment-524148">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/f1b6bd3a077b66e3b5610bfd8fa96ad9?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/f1b6bd3a077b66e3b5610bfd8fa96ad9?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Henar Domínguez Elvira</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-524148">July 3, 2019 at 6:44 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Hi! First of all thank you very much for all the tutorials,  I am learning a lot!</p>
<p>While doing the last part of this tutorial a found a problem that I do not know how to solve 🙁<br />
trying the code line &#8220;cnts = imutils.grab_contours(cnts)&#8221; it gives me an error saying &#8220;AttributeError: module &#8216;imutils&#8217; has no attribute &#8216;grab_contours&#8217; &#8221;</p>
<p>Do you know what could be the cause of the error?</p>
<p>Thank you very much again!</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-524355">
	<article id="article-comment-524355">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-524355">July 4, 2019 at 10:16 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>You need to upgrade your imutils install (you&#8217;re using an old version):</p>
<p><code>$ pip install --upgrade imutils</code></p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-even depth-1" id="comment-528176">
	<article id="article-comment-528176">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/03ab5f34b51f59359cbbd96f80f05558?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/03ab5f34b51f59359cbbd96f80f05558?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Etienne Bauscher</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-528176">July 29, 2019 at 9:49 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Thank you Adrian for investing in people. This is valuable information you are sharing here&#8230;</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-532760">
	<article id="article-comment-532760">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-532760">August 7, 2019 at 12:59 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Thanks Etienne 🙂</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-odd thread-alt depth-1" id="comment-528493">
	<article id="article-comment-528493">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/7685f39c99e139462b85e7f1bde1c165?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/7685f39c99e139462b85e7f1bde1c165?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Abhinav visen</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-528493">July 30, 2019 at 7:27 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Hey Adrian,<br />
Awesome blog by the way.<br />
A small doubt.<br />
Theoretically according to this threshold command :-<br />
cv2.threshold(gray, 225, 255, cv2.THRESH_BINARY_INV)[1]<br />
The essential output should be a region in figure  17 (below) with darker regions of the Tetris and lighter region in the white space.But essential our code gives the output in figure 19.Also can you explain the value [1] representing the function and what other image in the list does it returns.</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-532752">
	<article id="article-comment-532752">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-532752">August 7, 2019 at 12:53 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Hey Abhinav &#8212; if you need further help studying OpenCV I would recommend you read <a target="blank" href="https://www.pyimagesearch.com/practical-python-opencv/">Practical Python and OpenCV</a> where both your questions are answered.</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-even depth-1" id="comment-535719">
	<article id="article-comment-535719">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/8b06188d354c5e20747bb812283042b7?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/8b06188d354c5e20747bb812283042b7?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">dibora</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-535719">August 12, 2019 at 7:31 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Hi, i am just starting with computer vision and i wanted to get to the handy staff .Do you think i need to go deep in understanding the algorithms and mathematical aspects first?</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-539216">
	<article id="article-comment-539216">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-539216">August 16, 2019 at 5:43 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>No, at least not yet. Start with a practical education first. 1000s of PyImageSearch readers have used <a target="blank" href="https://www.pyimagesearch.com/practical-python-opencv/">Practical Python and OpenCV</a> to get their start in computer vision and OpenCV. I would definitely suggest starting there.</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-odd thread-alt depth-1" id="comment-565808">
	<article id="article-comment-565808">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/51b4594d042b67823646efaef3cabafd?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/51b4594d042b67823646efaef3cabafd?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">gabbyyy</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-565808">October 21, 2019 at 12:02 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Hi newbie here i have a problem in finding the contours and it&#8217;s so hard when i use different images for example i use image of cars via satellite and i want to count how many cars in there.</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-567115">
	<article id="article-comment-567115">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-567115">October 25, 2019 at 10:22 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Contours will not work well for detecting robust objects, especially if you cannot easily segment them. Try utilizing <a target="blank" href="https://www.pyimagesearch.com/start-here/#object_detection">object detection algorithms.</a></p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment odd alt depth-3" id="comment-567315">
	<article id="article-comment-567315">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/51b4594d042b67823646efaef3cabafd?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/51b4594d042b67823646efaef3cabafd?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">gabbyyy</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-567315">October 26, 2019 at 7:02 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Okay thanks 🙂 </p>
<p>Can i buy the practical python and opencv + case studies hardcopy without bundle?</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-4" id="comment-570782">
	<article id="article-comment-570782">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-570782">November 7, 2019 at 10:41 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>The hardcopy edition of Practical Python and OpenCV + Case Studies is only offered in the Hardcopy Bundle. As a self-published author, it&#8217;s not cheap to have copies of the books printed — I also manually fulfill all orders myself. In order to make the hardcopies feasible, I need to charge a little extra and provide a ton of added value through the virtual machine and video tutorials.</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-even depth-1" id="comment-566755">
	<article id="article-comment-566755">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/c15d13dfa70aa4bfb7c10bdea9d0e263?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/c15d13dfa70aa4bfb7c10bdea9d0e263?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Nikesh Prasad</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-566755">October 24, 2019 at 4:02 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Hi Adrian, </p>
<p>Thanks for this starter on OpenCV, both the tutorials were great.</p>
<p>I have 2 questions:</p>
<p>1. Why do we make a copy of image for erosion and dilation when the function does not erodes or dilates the image inplace?</p>
<p>2. How the bitwise_and is done in OpenCV?</p>
<p>Thank you.</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-567105">
	<article id="article-comment-567105">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-567105">October 25, 2019 at 10:17 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Thanks Nikesh, I&#8217;m glad you enjoyed the tutorial. If you need additional help I would recommend reading <a target="blank" href="https://www.pyimagesearch.com/practical-python-opencv/">Practical Python and OpenCV</a> to help you learn the OpenCV library.</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment odd alt depth-3" id="comment-567137">
	<article id="article-comment-567137">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/34ecab4faa912c3e6abc6f1fbecee79d?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/34ecab4faa912c3e6abc6f1fbecee79d?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Sanjay</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-567137">October 25, 2019 at 11:05 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>A nice tutorial Adrian.  You did not answer Nikesh. Even I have the same question. Why do you make a copy of the image before erode or dilate ? Does the original image change.</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-4" id="comment-570788">
	<article id="article-comment-570788">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-570788">November 7, 2019 at 10:44 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Hey Sanjay &#8212; I do my best to get to every question but I receive 200+ questions per day. If I&#8217;ve already answered a reader&#8217;s specific question in one of my existing blog posts, books, or courses, I link them to it (I cannot re-explain the same answers over and over as that would not be a good use of my time or yours). In this case, both your and Nikesh&#8217;s question is answered inside Practical Python and OpenCV.</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-odd thread-alt depth-1" id="comment-569449">
	<article id="article-comment-569449">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/7726e451b8b48fa05fedace9b3e205da?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/7726e451b8b48fa05fedace9b3e205da?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">cherif</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-569449">November 3, 2019 at 11:32 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Excellent course<br />
This tutorial push people to like OpenCv</p>
<p>Thank you very much!</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-570746">
	<article id="article-comment-570746">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-570746">November 7, 2019 at 10:24 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>You are welcome, I&#8217;m glad you enjoyed it! 🙂</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-even depth-1" id="comment-618056">
	<article id="article-comment-618056">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/4cacef8937b1a3db309c7ba456c6f66a?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/4cacef8937b1a3db309c7ba456c6f66a?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Anthony The Koala</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-618056">December 26, 2019 at 10:48 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Under the heading “rotating an image”, I wanted code that you would actually see an image rotate.</p>
<p>I wanted to animate the &#8216;image&#8217; over a series of angles. </p>
<p>That is I wanted to show and watch the image move. I was unable to achieve that even with a delay between successive angles. </p>
<p>The result was a grey screen with ONLY the final angled image showing.</p>
<p>Can you suggest a way to show and watch an &#8216;image&#8217; being rotated.</p>
<p>Thank you,<br />
Anthony of Sydney</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment even depth-2" id="comment-622453">
	<article id="article-comment-622453">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/4cacef8937b1a3db309c7ba456c6f66a?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/4cacef8937b1a3db309c7ba456c6f66a?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Anthony The Koala</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-622453">January 2, 2020 at 7:47 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Dear Dr Adrian,<br />
The very question may well be answered in your blog post titled <a href="https://www.pyimagesearch.com/2017/01/02/rotate-images-correctly-with-opencv-and-python/" rel="nofollow ugc">https://www.pyimagesearch.com/2017/01/02/rotate-images-correctly-with-opencv-and-python/</a> . In that tutorial you used the contours to extract the image of the pill leaving the background black.</p>
<p>I will be applying a version of the question I want answer myself by rotating the whole image without any contours. Then later I will experiment with the contours of which you have a few posts about that.</p>
<p>Thank you,<br />
Anthony of Sydney</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor odd alt depth-3" id="comment-622490">
	<article id="article-comment-622490">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-622490">January 2, 2020 at 8:46 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Hey Anthony, it sounds like you may have addressed your own question. Give the rotation tutorial a try.</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment even thread-odd thread-alt depth-1" id="comment-765925">
	<article id="article-comment-765925">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/ae94c323cf2296bdb9d1ca57082b05cd?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/ae94c323cf2296bdb9d1ca57082b05cd?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">mohamed elghazaly</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-765925">March 10, 2020 at 10:12 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Hello Adrian,<br />
V.interesting implementation but I &#8216;d like to ask if I can use ssim in comparing two images, each one is only a plain color but I compare the degree of color</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor odd alt depth-2" id="comment-766042">
	<article id="article-comment-766042">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-766042">March 11, 2020 at 4:47 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>What do you mean by &#8220;plain color&#8221;?</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment even thread-even depth-1" id="comment-767303">
	<article id="article-comment-767303">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/1485a97281e4563f8ad8c3bb17d6ee27?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/1485a97281e4563f8ad8c3bb17d6ee27?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Teja</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-767303">March 23, 2020 at 4:35 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Thanks a lot for wonderful hands on explanation&#8230; I love this blog and will continue to learn from it..</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor odd alt depth-2" id="comment-767652">
	<article id="article-comment-767652">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-767652">March 25, 2020 at 1:38 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Thanks so much Teja!</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment even thread-odd thread-alt depth-1" id="comment-767801">
	<article id="article-comment-767801">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/16f5fe6e9b41017ff9cb2ffaaeb73571?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/16f5fe6e9b41017ff9cb2ffaaeb73571?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">joshua</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-767801">March 26, 2020 at 8:06 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>thanks, Adrian<br />
As I am in lockdown I&#8217;m much interested to learn something where I could drift my skills and when I was googling about python with OpenCV to detect and recognize images I found you are clear with each explanation. thanks a lot and will leave a reply when I&#8217;m indeed .</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor odd alt depth-2" id="comment-769559">
	<article id="article-comment-769559">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-769559">April 1, 2020 at 9:43 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>It&#8217;s wonderful to hear you are using this time to study CV/DL, Joshua! Good luck and stay safe.</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment even thread-even depth-1" id="comment-767968">
	<article id="article-comment-767968">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/ae62f8621fa908222f1f26426450b1aa?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/ae62f8621fa908222f1f26426450b1aa?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Kondor</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-767968">March 27, 2020 at 12:33 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Awesome tutorials, I really like how you go step by step and explain every line. Thanks a lot! I like to run your code in blocks through jupyter notebook, and so far everything works just fine.</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor odd alt depth-2" id="comment-769558">
	<article id="article-comment-769558">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-769558">April 1, 2020 at 9:42 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Thanks Kondor!</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment even thread-odd thread-alt depth-1" id="comment-770397">
	<article id="article-comment-770397">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/ec8deded9b8aafc69c7acab12bca2f7a?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/ec8deded9b8aafc69c7acab12bca2f7a?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name"><a href="http://www.thetoiletpapercalculator.com" class="comment-author-link" rel="external nofollow">gomario</a></span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-770397">April 4, 2020 at 9:28 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Thanks! I&#8217;m stuck inside and have a few ideas that need image processing.  This has been a great help in getting me started and saving my insanity.</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment odd alt depth-2" id="comment-770398">
	<article id="article-comment-770398">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/ec8deded9b8aafc69c7acab12bca2f7a?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/ec8deded9b8aafc69c7acab12bca2f7a?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">gomario</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-770398">April 4, 2020 at 9:30 pm</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Oops, no edit option so &#8230;.   insanity == sanity 🙂</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-3" id="comment-772510">
	<article id="article-comment-772510">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-772510">April 9, 2020 at 9:18 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Thanks Gomario 🙂</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->

	<li class="comment odd alt thread-even depth-1" id="comment-779798">
	<article id="article-comment-779798">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/003cc47e4929da86b76923e010c7c4ec?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/003cc47e4929da86b76923e010c7c4ec?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Mangesh</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-779798">April 13, 2020 at 6:54 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Hello Adrian,</p>
<p>I am going through your 17 day crash course and I am very happy with the results. </p>
<p>(I have no experience in coding, but from last week after visiting your website, I am able to run some test codes on my own.)</p>
<p>My target was to create a test project which work as below.</p>
<p>#Count circles in a high speed video feed coming from webcam or digicam.<br />
#Number the detected circles sequentially (i.e. 1,2,3,4 and on).<br />
#After a certain count print the total circle count number in csv file.<br />
#After print in csv, I want to continue with my circle counting.</p>
<p>Can I able to write this code on my own after reading all your mails.</p>
<p>Thanks for your guidance.</p>
		</div>

		
		
	</article>
	<ul class="children">

	<li class="comment byuser comment-author-adrian bypostauthor even depth-2" id="comment-785462">
	<article id="article-comment-785462">

		
		<header class="comment-header">
			<p class="comment-author">
				<img alt='' src='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=48&#038;d=mm&#038;r=g' srcset='https://secure.gravatar.com/avatar/02743529311d3b8babbaf6935670ec9c?s=96&#038;d=mm&#038;r=g 2x' class='avatar avatar-48 photo' height='48' width='48' /><span class="comment-author-name">Adrian Rosebrock</span>			</p>

			<p class="comment-meta"><time class="comment-time"><a class="comment-time-link" href="https://www.pyimagesearch.com/2018/07/19/opencv-tutorial-a-guide-to-learn-opencv/#comment-785462">April 16, 2020 at 7:57 am</a></time></p>		</header>

		<div class="comment-content">
			
			<p>Hey Mangesh, I&#8217;m confident that after going through the crash course that you will be able to make strides to completing your project. I can&#8217;t say for certain if you will be able to complete it (as I don&#8217;t know the project details) but I&#8217;m sure you&#8217;ll be able to make massive headway on it.</p>
		</div>

		
		
	</article>
	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->
</ol></div><div class="comment-policy">  <h3 class="comment-policy__title">Before you leave a comment...</h3>  <div class="comment-policy__content"><p>Hey, Adrian here, author of the PyImageSearch blog. I&#8217;d love to hear from you; however, I am super busy with some special projects right now and do not have the time to moderate and personally respond to blog post comments.</p>
<p>I&#8217;d be happy to help you with your question or project, but <a href="https://www.pyimagesearch.com/books-and-courses/" target="_blank" rel="noopener noreferrer" data-token-index="1" data-reactroot="">I have to politely ask you to purchase one of my books or courses first.</a></p>
<p>Why bother becoming a PyImageSearch customer?</p>
<ul>
<li>You&#8217;ll receive a <strong>great education</strong> through my premium content</li>
<li>You&#8217;ll receive <strong>priority support</strong></li>
<li>You&#8217;ll receive a <strong>guaranteed response </strong>from myself and my team</li>
<li>You&#8217;ll be able to <strong>confidently and successfully</strong> apply Computer Vision, Deep Learning, and OpenCV to your projects</li>
</ul>
<p><a href="https://www.pyimagesearch.com/books-and-courses/" target="_blank" rel="noopener noreferrer" data-token-index="0" data-reactroot="">Click here to see my full catalog of books and courses.</a> Take a look and I hope to see you on the other side!</p>
</div></div></main><aside class="sidebar sidebar-primary widget-area" role="complementary" aria-label="Primary Sidebar" id="genesis-sidebar-primary"><h2 class="genesis-sidebar-title screen-reader-text">Primary Sidebar</h2><section id="custom_html-2" class="widget_text widget widget_custom_html"><div class="widget_text widget-wrap"><div class="textwidget custom-html-widget"><div class="sidebar__block">
	<a href="https://app.monstercampaigns.com/c/mdoijtrmex7bpm0rp2hn/"><img src="https://www.pyimagesearch.com/wp-content/uploads/2020/01/free-crashcourse-200x300-1.jpg" alt="" class="wp-image-11900" width="125" height="188" srcset="https://www.pyimagesearch.com/wp-content/uploads/2020/01/free-crashcourse-200x300-1.jpg 500w, https://www.pyimagesearch.com/wp-content/uploads/2020/01/free-crashcourse-200x300-1.jpg 200w" sizes="(max-width: 125px) 100vw, 125px"></a>	
	<h4 class="sidebar__block-title"><a href="https://app.monstercampaigns.com/c/mdoijtrmex7bpm0rp2hn/">Free Resource Guide: Computer Vision, OpenCV, and Deep Learning</a></h4>
	<div class="sidebar__block-content">
		<p>Inside you'll find my hand-picked tutorials, books, courses, and libraries to help you master CV and DL.</p>	
	</div>
	<a href="https://app.monstercampaigns.com/c/mdoijtrmex7bpm0rp2hn/" class="button sidebar__block-button">Download</a>
</div></div></div></section>
<section id="custom_html-3" class="widget_text widget widget_custom_html"><div class="widget_text widget-wrap"><div class="textwidget custom-html-widget"><div class="sidebar__block">
	<a target="_blank" href="https://www.pyimagesearch.com/raspberry-pi-for-computer-vision/" rel="noopener noreferrer"><img src="https://www.pyimagesearch.com/wp-content/uploads/2020/01/raspberry-pi-for-computer-vision-200x300-1.jpg" alt="" class="wp-image-11905" width="125" height="188" srcset="https://www.pyimagesearch.com/wp-content/uploads/2020/01/raspberry-pi-for-computer-vision-200x300-1.jpg 500w, https://www.pyimagesearch.com/wp-content/uploads/2020/01/raspberry-pi-for-computer-vision-200x300-1.jpg 200w" sizes="(max-width: 125px) 100vw, 125px"></a>	
	<h4 class="sidebar__block-title"><a target="_blank" href="https://www.pyimagesearch.com/raspberry-pi-for-computer-vision/" rel="noopener noreferrer">Raspberry Pi for Computer Vision</a></h4>
	<div class="sidebar__block-content">
		<p>You can teach your Raspberry Pi to “see” using Computer Vision, Deep Learning, and OpenCV. Let me show you how.</p>	
	</div>
	<a target="_blank" href="https://www.pyimagesearch.com/raspberry-pi-for-computer-vision/" class="sidebar__block-link" rel="noopener noreferrer">Learn More</a>
</div></div></div></section>
<section id="custom_html-4" class="widget_text widget widget_custom_html"><div class="widget_text widget-wrap"><div class="textwidget custom-html-widget"><div class="sidebar__block">
	<a target="_blank" href="https://www.pyimagesearch.com/deep-learning-computer-vision-python-book/" rel="noopener noreferrer"><img src="https://www.pyimagesearch.com/wp-content/uploads/2020/01/deep-learning-for-computer-vision-200x300-1.jpg" alt="" class="wp-image-11907" width="125" height="188" srcset="https://www.pyimagesearch.com/wp-content/uploads/2020/01/deep-learning-for-computer-vision-200x300-1.jpg 500w, https://www.pyimagesearch.com/wp-content/uploads/2020/01/deep-learning-for-computer-vision-200x300-1.jpg 200w" sizes="(max-width: 125px) 100vw, 125px"></a>	
	<h4 class="sidebar__block-title"><a target="_blank" href="https://www.pyimagesearch.com/deep-learning-computer-vision-python-book/" rel="noopener noreferrer">Deep Learning for Computer Vision with Python</a></h4>
	<div class="sidebar__block-content">
		<p>You're interested in deep learning and computer vision, but you don't know how to get started. Let me help. My new book will teach you all you need to know about deep learning.</p>	
	</div>
	<a target="_blank" href="https://www.pyimagesearch.com/deep-learning-computer-vision-python-book/" class="sidebar__block-link" rel="noopener noreferrer">Learn More</a>
</div></div></div></section>
<section id="custom_html-5" class="widget_text widget widget_custom_html"><div class="widget_text widget-wrap"><div class="textwidget custom-html-widget"><div class="sidebar__block">
<h4 class="sidebar__block-title"><a target="_blank" href="https://www.pyimagesearch.com/practical-python-opencv/" rel="noopener noreferrer">You can detect faces in images & video.</a></h4>	
<a target="_blank" href="https://www.pyimagesearch.com/practical-python-opencv/" rel="noopener noreferrer"><img src="https://hcl.pyimagesearch.com/wp-content/uploads/2020/01/detect-faces.jpg" alt="" class="wp-image-11909"></a>	
<div class="sidebar__block-content">
<p>Are you interested in detecting faces in images & video? But tired of Googling for tutorials that never work? Then let me help! I guarantee that my new book will turn you into a face detection ninja by the end of this weekend. Click here to give it a shot yourself.</p>
</div>
<a target="_blank" href="https://www.pyimagesearch.com/practical-python-opencv/" class="sidebar__block-link" rel="noopener noreferrer">Learn More</a>
</div></div></div></section>
<section id="custom_html-6" class="widget_text widget widget_custom_html"><div class="widget_text widget-wrap"><div class="textwidget custom-html-widget"><div class="sidebar__block">
<h4 class="sidebar__block-title"><a target="_blank" href="https://www.pyimagesearch.com/pyimagesearch-gurus/" rel="noopener noreferrer">PyImageSearch Gurus: NOW ENROLLING!</a></h4>	
<a target="_blank" href="https://www.pyimagesearch.com/pyimagesearch-gurus/" rel="noopener noreferrer"><img src="https://www.pyimagesearch.com/wp-content/uploads/2020/01/gurus-course-200x300-1.jpg" alt="" class="wp-image-11903" width="125" height="188" srcset="https://www.pyimagesearch.com/wp-content/uploads/2020/01/gurus-course-200x300-1.jpg 500w, https://www.pyimagesearch.com/wp-content/uploads/2020/01/gurus-course-200x300-1.jpg 200w" sizes="(max-width: 125px) 100vw, 125px"></a>
<div class="sidebar__block-content">
<p>The PyImageSearch Gurus course is now enrolling! Inside the course you'll learn how to perform:</p>
<p>
<strong>
                &middot; Automatic License Plate Recognition (ANPR)<br>&middot; Deep Learning<br>&middot; Face Recognition<br>&middot; <em>...and much more!</em>
</strong>
</p>
<p>
Click the button below to learn more about the course, take a tour, and get 10 (FREE) sample lessons.
</p>
</div>
<a target="_blank" href="https://www.pyimagesearch.com/pyimagesearch-gurus/" class="sidebar__block-link" rel="noopener noreferrer">Learn More</a>
</div></div></div></section>
</aside></div></div></div><div class="similar-articles"><div class="wrap"><h3>Similar articles</h3><div class="gpd-simple-card-group"><article class="post-summary"><a href="https://www.pyimagesearch.com/2015/06/15/install-opencv-3-0-and-python-2-7-on-osx/" class="post-summary--link"><header class="entry-header"><div class="entry-categories"><div class="entry-category">OpenCV Tutorials</div><div class="entry-category">Tutorials</div></div><h2 class="entry-title">Install OpenCV 3.0 and Python 2.7+ on OSX</h2><div class="entry-date">June 15, 2015</div></header><p class="entry-content-link"><svg class="svg-icon long-arrow" width="14" height="14" aria-hidden="true" role="img" focusable="false" width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M6.8125 0.1875C6.875 0.125 6.96875 0.09375 7.09375 0.09375C7.1875 0.09375 7.28125 0.125 7.34375 0.1875L13.875 6.75C13.9375 6.8125 14 6.90625 14 7C14 7.125 13.9375 7.1875 13.875 7.25L7.34375 13.8125C7.28125 13.875 7.1875 13.9062 7.09375 13.9062C6.96875 13.9062 6.875 13.875 6.8125 13.8125L6.1875 13.1875C6.125 13.125 6.09375 13.0625 6.09375 12.9375C6.09375 12.8438 6.125 12.75 6.1875 12.6562L11.0312 7.8125H0.375C0.25 7.8125 0.15625 7.78125 0.09375 7.71875C0.03125 7.65625 0 7.5625 0 7.4375V6.5625C0 6.46875 0.03125 6.375 0.09375 6.3125C0.15625 6.25 0.25 6.1875 0.375 6.1875H11.0312L6.1875 1.34375C6.125 1.28125 6.09375 1.1875 6.09375 1.0625C6.09375 0.96875 6.125 0.875 6.1875 0.8125L6.8125 0.1875Z" fill="#169FE6"/></svg></p></a></article><article class="post-summary"><a href="https://www.pyimagesearch.com/2016/06/13/considerations-when-setting-up-deep-learning-hardware/" class="post-summary--link"><header class="entry-header"><div class="entry-categories"><div class="entry-category">Deep Learning</div><div class="entry-category">Resources</div></div><h2 class="entry-title">Considerations when setting up deep learning hardware</h2><div class="entry-date">June 13, 2016</div></header><p class="entry-content-link"><svg class="svg-icon long-arrow" width="14" height="14" aria-hidden="true" role="img" focusable="false" width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M6.8125 0.1875C6.875 0.125 6.96875 0.09375 7.09375 0.09375C7.1875 0.09375 7.28125 0.125 7.34375 0.1875L13.875 6.75C13.9375 6.8125 14 6.90625 14 7C14 7.125 13.9375 7.1875 13.875 7.25L7.34375 13.8125C7.28125 13.875 7.1875 13.9062 7.09375 13.9062C6.96875 13.9062 6.875 13.875 6.8125 13.8125L6.1875 13.1875C6.125 13.125 6.09375 13.0625 6.09375 12.9375C6.09375 12.8438 6.125 12.75 6.1875 12.6562L11.0312 7.8125H0.375C0.25 7.8125 0.15625 7.78125 0.09375 7.71875C0.03125 7.65625 0 7.5625 0 7.4375V6.5625C0 6.46875 0.03125 6.375 0.09375 6.3125C0.15625 6.25 0.25 6.1875 0.375 6.1875H11.0312L6.1875 1.34375C6.125 1.28125 6.09375 1.1875 6.09375 1.0625C6.09375 0.96875 6.125 0.875 6.1875 0.8125L6.8125 0.1875Z" fill="#169FE6"/></svg></p></a></article><article class="post-summary"><a href="https://www.pyimagesearch.com/2019/07/22/keras-learning-rate-schedules-and-decay/" class="post-summary--link"><header class="entry-header"><div class="entry-categories"><div class="entry-category">Deep Learning</div><div class="entry-category">Keras and TensorFlow</div><div class="entry-category">Tutorials</div></div><h2 class="entry-title">Keras learning rate schedules and decay</h2><div class="entry-date">July 22, 2019</div></header><p class="entry-content-link"><svg class="svg-icon long-arrow" width="14" height="14" aria-hidden="true" role="img" focusable="false" width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M6.8125 0.1875C6.875 0.125 6.96875 0.09375 7.09375 0.09375C7.1875 0.09375 7.28125 0.125 7.34375 0.1875L13.875 6.75C13.9375 6.8125 14 6.90625 14 7C14 7.125 13.9375 7.1875 13.875 7.25L7.34375 13.8125C7.28125 13.875 7.1875 13.9062 7.09375 13.9062C6.96875 13.9062 6.875 13.875 6.8125 13.8125L6.1875 13.1875C6.125 13.125 6.09375 13.0625 6.09375 12.9375C6.09375 12.8438 6.125 12.75 6.1875 12.6562L11.0312 7.8125H0.375C0.25 7.8125 0.15625 7.78125 0.09375 7.71875C0.03125 7.65625 0 7.5625 0 7.4375V6.5625C0 6.46875 0.03125 6.375 0.09375 6.3125C0.15625 6.25 0.25 6.1875 0.375 6.1875H11.0312L6.1875 1.34375C6.125 1.28125 6.09375 1.1875 6.09375 1.0625C6.09375 0.96875 6.125 0.875 6.1875 0.8125L6.8125 0.1875Z" fill="#169FE6"/></svg></p></a></article></div></div></div><div class="gpd-footer-cta"><div class="wrap"><div class="footer-cta-grid"><div class="footer-cta-image"><img width="932" height="833" src="https://www.pyimagesearch.com/wp-content/uploads/2020/02/man-on-sofa-with-laptop-1.jpg" class="attachment-full size-full" alt="" srcset="https://www.pyimagesearch.com/wp-content/uploads/2020/02/man-on-sofa-with-laptop-1.jpg 932w, https://www.pyimagesearch.com/wp-content/uploads/2020/02/man-on-sofa-with-laptop-1-300x268.jpg 300w, https://www.pyimagesearch.com/wp-content/uploads/2020/02/man-on-sofa-with-laptop-1-768x686.jpg 768w" sizes="(max-width: 932px) 100vw, 932px" /></div><div class="footer-cta-title"><h3>You can learn Computer Vision, Deep Learning, and OpenCV.</h3></div><div class="footer-cta-content"><div class="footer-cta-content-desc"><p>Get your FREE 17 page Computer Vision, OpenCV, and Deep Learning Resource Guide PDF. Inside you&#8217;ll find my hand-picked tutorials, books, courses, and libraries to help you master CV and DL.</p>
</div><div class="footer-cta-content-action"><form class="footer-cta" action="https://www.getdrip.com/forms/657075648/submissions" method="post" target="_blank" data-drip-embedded-form="657075648">
	<input type="email" name="fields[email]" class="form-control" id="email" value="" placeholder="Your email address"/>
	<button type="submit" data-drip-attribute="sign-up-button">Download for free</button>
	<div style="display: none;" aria-hidden="true"><label for="website">Website</label><br /><input type="text" id="website" name="website" tabindex="-1" autocomplete="false" value="" /></div>
</form></div></div></div></div></div><div class="footer-widgets" id="genesis-footer-widgets"><h2 class="genesis-sidebar-title screen-reader-text">Footer</h2><div class="wrap"><div class="widget-area footer-widgets-1 footer-widget-area"><section id="custom_html-7" class="widget_text widget widget_custom_html"><div class="widget_text widget-wrap"><h3 class="widgettitle widget-title">Topics</h3>
<div class="textwidget custom-html-widget"><ul>
	<li><a href="https://www.pyimagesearch.com/category/deep-learning-2/">Deep Learning</a></li>
	<li><a href="https://www.pyimagesearch.com/category/dlib/">Dlib Library</a></li>
	<li><a href="https://www.pyimagesearch.com/category/embedded/">Embedded/IoT and Computer Vision</a></li>
	<li><a href="https://www.pyimagesearch.com/category/faces/">Face Applications</a></li>
	<li><a href="https://www.pyimagesearch.com/category/image-processing/">Image Processing</a></li>
	<li><a href="https://www.pyimagesearch.com/category/interviews/">Interviews</a></li>
	<li><a href="https://www.pyimagesearch.com/category/keras/">Keras</a></li>
</ul>
</div></div></section>
</div><div class="widget-area footer-widgets-2 footer-widget-area"><section id="custom_html-8" class="widget_text widget widget_custom_html"><div class="widget_text widget-wrap"><div class="textwidget custom-html-widget"><ul>
	<li><a href="https://www.pyimagesearch.com/category/machine-learning-2/">Machine Learning and Computer Vision</a></li>
	<li><a href="https://www.pyimagesearch.com/category/medical/">Medical Computer Vision</a></li>
	<li><a href="https://www.pyimagesearch.com/category/optical-character-recognition-ocr/">Optical Character Recognition (OCR)</a></li>
	<li><a href="https://www.pyimagesearch.com/category/object-detection/">Object Detection</a></li>
	<li><a href="https://www.pyimagesearch.com/category/object-tracking/">Object Tracking</a></li>
	<li><a href="https://www.pyimagesearch.com/category/opencv/">OpenCV Tutorials</a></li>
	<li><a href="https://www.pyimagesearch.com/category/raspberry-pi/">Raspberry Pi</a></li>
</ul></div></div></section>
</div><div class="widget-area footer-widgets-3 footer-widget-area"><section id="custom_html-9" class="widget_text widget widget_custom_html"><div class="widget_text widget-wrap"><h3 class="widgettitle widget-title">Books &#038; Courses</h3>
<div class="textwidget custom-html-widget"><ul>
<li><a href="https://www.pyimagesearch.com/free-opencv-computer-vision-deep-learning-crash-course/">FREE CV, DL, and OpenCV Crash Course</a></li>
<li><a href="https://www.pyimagesearch.com/practical-python-opencv/">Practical Python and OpenCV</a></li>
<li><a href="https://www.pyimagesearch.com/deep-learning-computer-vision-python-book/">Deep Learning for Computer Vision with Python</a></li>
<li><a href="https://www.pyimagesearch.com/pyimagesearch-gurus/">PyImageSearch Gurus Course</a></li>
<li><a href="https://www.pyimagesearch.com/raspberry-pi-for-computer-vision/">Raspberry Pi for Computer Vision</a></li>
</ul></div></div></section>
</div><div class="widget-area footer-widgets-4 footer-widget-area"><section id="custom_html-10" class="widget_text widget widget_custom_html"><div class="widget_text widget-wrap"><h3 class="widgettitle widget-title">PyImageSearch</h3>
<div class="textwidget custom-html-widget"><ul>
	<li><a href="https://www.pyimagesearch.com/start-here/">Get Started</a></li>
	<li><a href="https://www.pyimagesearch.com/opencv-tutorials-resources-guides/">OpenCV Install Guides</a></li>
	<li><a href="https://www.pyimagesearch.com/about/">About</a></li>
	<li><a href="https://www.pyimagesearch.com/faqs/">FAQ</a></li>
	<li><a href="https://www.pyimagesearch.com/topics/">Blog</a></li>
	<li><a href="https://www.pyimagesearch.com/contact/">Contact</a></li>
	<li><a href="https://www.pyimagesearch.com/privacy-policy/">Privacy Policy</a></li>
</ul></div></div></section>
</div></div></div><footer class="site-footer"><div class="wrap"><div class="footer-logo"><p class="site-title"><a href="https://www.pyimagesearch.com"></a></p></div><div class="footer-social"><a target="_blank" href="https://www.facebook.com/pyimagesearch"><svg class="svg-icon social-icon" width="18" height="18" aria-hidden="true" role="img" focusable="false" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 264 512"><path d="M215.8 85H264V3.6C255.7 2.5 227.1 0 193.8 0 124.3 0 76.7 42.4 76.7 120.3V192H0v91h76.7v229h94V283h73.6l11.7-91h-85.3v-62.7c0-26.3 7.3-44.3 45.1-44.3z"/></svg></a><a target="_blank" href="https://twitter.com/PyImageSearch"><svg class="svg-icon social-icon" width="18" height="18" aria-hidden="true" role="img" focusable="false" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M459.37 151.716c.325 4.548.325 9.097.325 13.645 0 138.72-105.583 298.558-298.558 298.558-59.452 0-114.68-17.219-161.137-47.106 8.447.974 16.568 1.299 25.34 1.299 49.055 0 94.213-16.568 130.274-44.832-46.132-.975-84.792-31.188-98.112-72.772 6.498.974 12.995 1.624 19.818 1.624 9.421 0 18.843-1.3 27.614-3.573-48.081-9.747-84.143-51.98-84.143-102.985v-1.299c13.969 7.797 30.214 12.67 47.431 13.319-28.264-18.843-46.781-51.005-46.781-87.391 0-19.492 5.197-37.36 14.294-52.954 51.655 63.675 129.3 105.258 216.365 109.807-1.624-7.797-2.599-15.918-2.599-24.04 0-57.828 46.782-104.934 104.934-104.934 30.213 0 57.502 12.67 76.67 33.137 23.715-4.548 46.456-13.32 66.599-25.34-7.798 24.366-24.366 44.833-46.132 57.827 21.117-2.273 41.584-8.122 60.426-16.243-14.292 20.791-32.161 39.308-52.628 54.253z"/></svg></a><a target="_blank" href="http://www.linkedin.com/pub/adrian-rosebrock/2a/873/59b"><svg class="svg-icon social-icon" width="18" height="18" aria-hidden="true" role="img" focusable="false" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M416 32H31.9C14.3 32 0 46.5 0 64.3v383.4C0 465.5 14.3 480 31.9 480H416c17.6 0 32-14.5 32-32.3V64.3c0-17.8-14.4-32.3-32-32.3zM135.4 416H69V202.2h66.5V416zm-33.2-243c-21.3 0-38.5-17.3-38.5-38.5S80.9 96 102.2 96c21.2 0 38.5 17.3 38.5 38.5 0 21.3-17.2 38.5-38.5 38.5zm282.1 243h-66.4V312c0-24.8-.5-56.7-34.5-56.7-34.6 0-39.9 27-39.9 54.9V416h-66.4V202.2h63.7v29.2h.9c8.9-16.8 30.6-34.5 62.9-34.5 67.2 0 79.7 44.3 79.7 101.9V416z"/></svg></a><a target="_blank" href="https://www.youtube.com/channel/UCoQK7OVcIVy-nV4m-SMCk_Q/videos"><svg class="svg-icon social-icon" width="18" height="18" aria-hidden="true" role="img" focusable="false" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512"><path d="M549.655 124.083c-6.281-23.65-24.787-42.276-48.284-48.597C458.781 64 288 64 288 64S117.22 64 74.629 75.486c-23.497 6.322-42.003 24.947-48.284 48.597-11.412 42.867-11.412 132.305-11.412 132.305s0 89.438 11.412 132.305c6.281 23.65 24.787 41.5 48.284 47.821C117.22 448 288 448 288 448s170.78 0 213.371-11.486c23.497-6.321 42.003-24.171 48.284-47.821 11.412-42.867 11.412-132.305 11.412-132.305s0-89.438-11.412-132.305zm-317.51 213.508V175.185l142.739 81.205-142.739 81.201z"/></svg></a></div><div class="footer-info">&copy; 2020 <a href="https://www.pyimagesearch.com">PyImageSearch</a>. All Rights Reserved.</div></div></footer></div><!-- RightMessage -->
<script type="text/javascript"> 
(function(p, a, n, d, o, b) {
    o = n.createElement('script'); o.type = 'text/javascript'; o.async = true; o.src = 'https://tag.rightmessage.com/'+p+'.js';
    b = n.getElementsByTagName('script')[0]; b.parentNode.insertBefore(o, b);
    d = function(h, u, i) { var o = n.createElement('style'); o.id = 'rmcloak'+i; o.type = 'text/css';
        o.appendChild(n.createTextNode('.rmcloak'+h+'{visibility:hidden}.rmcloak'+u+'{display:none}'));
        b.parentNode.insertBefore(o, b); return o; }; o = d('', '-hidden', ''); d('-stay-invisible', '-stay-hidden', '-stay');
    setTimeout(function() { o.parentNode && o.parentNode.removeChild(o); }, a);
})('1871593262', 2500, document);
</script><!-- Drip -->
<script type="text/javascript">
  var _dcq = _dcq || [];
  var _dcs = _dcs || {}; 
  _dcs.account = '4768429';
  
  (function() {
    var dc = document.createElement('script');
    dc.type = 'text/javascript'; dc.async = true; 
    dc.src = '//tag.getdrip.com/4768429.js';
    var s = document.getElementsByTagName('script')[0];
    s.parentNode.insertBefore(dc, s);
  })();
</script>

<!-- facebook -->
<script>
  !function(f,b,e,v,n,t,s)
  {if(f.fbq)return;n=f.fbq=function(){n.callMethod?
  n.callMethod.apply(n,arguments):n.queue.push(arguments)};
  if(!f._fbq)f._fbq=n;n.push=n;n.loaded=!0;n.version='2.0';
  n.queue=[];t=b.createElement(e);t.async=!0;
  t.src=v;s=b.getElementsByTagName(e)[0];
  s.parentNode.insertBefore(t,s)}(window, document,'script',
  'https://connect.facebook.net/en_US/fbevents.js');
  fbq('init', '1465896023527386');
  fbq('track', 'PageView');
</script>
<noscript><img height="1" width="1" style="display:none"
  src="https://www.facebook.com/tr?id=1465896023527386&ev=PageView&noscript=1"
/></noscript>

<!-- Google Analytics -->
<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//web.archive.org/web/20170924062416/https://www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-46641058-1', 'pyimagesearch.com');
  ga('send', 'pageview');
</script>

<! -- Clicky -->
<script src="//static.getclicky.com/js" type="text/javascript"></script>
<script type="text/javascript">try{ clicky.init(101083980); }catch(e){}</script><!-- This site is converting visitors into subscribers and customers with OptinMonster - https://optinmonster.com :: Campaign Title: CS: Template --><script type="text/javascript" src="https://a.optmnstr.com/app/js/api.min.js" data-campaign="tortsem7qkvyuxc4cyfi" data-user="18464" data-env="production"></script><!-- / OptinMonster --><!-- This site is converting visitors into subscribers and customers with OptinMonster - https://optinmonster.com :: Campaign Title: CVDL Resource Guide --><script type="text/javascript" src="https://a.optmnstr.com/app/js/api.min.js" data-campaign="mdoijtrmex7bpm0rp2hn" data-user="18464" data-env="production"></script><!-- / OptinMonster --><div style="position:absolute;overflow:hidden;clip:rect(0 0 0 0);height:1px;width:1px;margin:-1px;padding:0;border:0"><div class="omapi-shortcode-helper">[email]</div><div class="omapi-shortcode-parsed omapi-encoded">[email]</div></div>		<script type="text/javascript">var tortsem7qkvyuxc4cyfi_shortcode = true;var mdoijtrmex7bpm0rp2hn_shortcode = true;</script>
		<script type='text/javascript'>
/* <![CDATA[ */
var wpcf7 = {"apiSettings":{"root":"https:\/\/www.pyimagesearch.com\/wp-json\/contact-form-7\/v1","namespace":"contact-form-7\/v1"},"cached":"1"};
/* ]]> */
</script>
<script src="https://www.pyimagesearch.com/wp-content/cache/minify/0fef6.js"></script>

<script type='text/javascript' src='https://www.google.com/recaptcha/api.js?render=6LcSHsQUAAAAAIzvikURE5e1jZ-YAGgyhpZnfS6o&#038;ver=3.0'></script>
<script src="https://www.pyimagesearch.com/wp-content/cache/minify/707d8.js"></script>

<script type='text/javascript'>
/* <![CDATA[ */
var pyISOptinMonster = {"post_title":"OpenCV Tutorial: A Guide to Learn OpenCV","campaign_id":"tortsem7qkvyuxc4cyfi","form_image":"https:\/\/s3-us-west-2.amazonaws.com\/static.pyimagesearch.com\/optins\/cs_opencv_tutorial.png","drip_form_submission_url":"https:\/\/www.getdrip.com\/forms\/878670517\/submissions","drip_id":"878670517"};
/* ]]> */
</script>







<script src="https://www.pyimagesearch.com/wp-content/cache/minify/20a88.js"></script>

<script type='text/javascript'>
!function(n,o){"undefined"!=typeof EnlighterJS?(n.EnlighterJSINIT=function(){EnlighterJS.init("pre.EnlighterJSRAW", "code.EnlighterJSRAW", {"indent":-1,"ampersandCleanup":true,"linehover":false,"rawcodeDbclick":false,"textOverflow":"break","linenumbers":true,"theme":"pyis-enlighter-theme","retainCssClasses":false})})():(o&&(o.error||o.log)||function(){})("Error: EnlighterJS resources not loaded yet!")}(window,console);
</script>

<script src="https://www.pyimagesearch.com/wp-content/cache/minify/69a5c.js"></script>

<script type="text/javascript">
( function( grecaptcha, sitekey, actions ) {

	var wpcf7recaptcha = {

		execute: function( action ) {
			grecaptcha.execute(
				sitekey,
				{ action: action }
			).then( function( token ) {
				var forms = document.getElementsByTagName( 'form' );

				for ( var i = 0; i < forms.length; i++ ) {
					var fields = forms[ i ].getElementsByTagName( 'input' );

					for ( var j = 0; j < fields.length; j++ ) {
						var field = fields[ j ];

						if ( 'g-recaptcha-response' === field.getAttribute( 'name' ) ) {
							field.setAttribute( 'value', token );
							break;
						}
					}
				}
			} );
		},

		executeOnHomepage: function() {
			wpcf7recaptcha.execute( actions[ 'homepage' ] );
		},

		executeOnContactform: function() {
			wpcf7recaptcha.execute( actions[ 'contactform' ] );
		},

	};

	grecaptcha.ready(
		wpcf7recaptcha.executeOnHomepage
	);

	document.addEventListener( 'change',
		wpcf7recaptcha.executeOnContactform, false
	);

	document.addEventListener( 'wpcf7submit',
		wpcf7recaptcha.executeOnHomepage, false
	);

} )(
	grecaptcha,
	'6LcSHsQUAAAAAIzvikURE5e1jZ-YAGgyhpZnfS6o',
	{"homepage":"homepage","contactform":"contactform"}
);
</script>
		<script type="text/javascript">var omapi_localized = { ajax: 'https://www.pyimagesearch.com/wp-admin/admin-ajax.php?optin-monster-ajax-route=1', nonce: '132cf08714', slugs: {"tortsem7qkvyuxc4cyfi":{"slug":"tortsem7qkvyuxc4cyfi","mailpoet":false},"mdoijtrmex7bpm0rp2hn":{"slug":"mdoijtrmex7bpm0rp2hn","mailpoet":false}} };</script>
				<script type="text/javascript">var omapi_data = {"wc_cart":[],"object_id":7642,"object_key":"post","object_type":"post","term_ids":[572,27,469,80,106,75,76,4,15,17,164]};</script>
		</body></html>

<!--
Performance optimized by W3 Total Cache. Learn more: https://www.w3-edge.com/products/

Object Caching 208/332 objects using disk
Page Caching using disk: enhanced 
Minified using disk
Database Caching 4/27 queries in 0.038 seconds using disk

Served from: www.pyimagesearch.com @ 2020-04-28 20:38:35 by W3 Total Cache
-->