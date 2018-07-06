# soft
<!DOCTYPE html>
<!--[if lt IE 7]>      <html class="no-js lt-ie9 lt-ie8 lt-ie7"> <![endif]-->
<!--[if IE 7]>         <html class="no-js lt-ie9 lt-ie8"> <![endif]-->
<!--[if IE 8]>         <html class="no-js lt-ie9"> <![endif]-->
<!--[if gt IE 8]><!--> <html class="no-js"> <!--<![endif]-->
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
    <title>{Title}{block:PostTitle}: {PostTitle}{/block:PostTitle}</title>
    {block:Description}
    <meta name="description" content="{MetaDescription}">
    {/block:Description}
    <meta name="viewport" content="width=device-width">

    <!-- Tumblr Theme configuration -->
    <meta name="color:Background" content="#FFFFFF"/>
    <meta name="color:Text" content="#000000"/>
    <meta name="color:Link" content="#0000FF"/>
    <meta name="color:Link Hover" content="#FF0000"/>
    <meta name="color:Link Visited" content="#800080"/>

    <meta name="font:Site Font" content=""/>

    <meta name="text:Footer Text" content=""/>
    <meta name="text:Google Analytics ID" content=""/>

    <meta name="image:Header" content=""/>

    <meta name="if:Show Archive" content="1"/>
    <meta name="if:Show RSS" content="0"/>
    <meta name="if:Show Search" content="0"/>

    <meta name="if:Use Time Ago" content="0"/>
    <meta name="if:Use HighRes Photos" content="1"/>
    <meta name="if:Use Number Pagination" content="0"/>

    <!-- END Tumblr Theme configuration -->

    <link rel="shortcut icon" href="{Favicon}">
    <link rel="apple-touch-icon" href="{PortraitURL-128}">
    <link rel="alternate" type="application/rss+xml" href="{RSS}">

    <link rel="stylesheet" href="https://raw.github.com/wxrod/Tumblr-HTML5-Blank-Theme/master/css/normalize.min.css">

    <script src="https://raw.github.com/wxrod/Tumblr-HTML5-Blank-Theme/master/js/vendor/modernizr.min.js"></script>

    <style type="text/css">
      body{
        background:{color:Background};
        font-family:{font:Site Font};
        color:{color:Text};
      }
      a{
        color:{color:Link};
      }
      a:hover{
        color:{color:Link Hover};
      }
      a:visited{
        color:{color:Link Visited};
      }
      {CustomCSS}
    </style>
  </head>
  <body>
    <!--[if lt IE 7]>
    <p class="chromeframe">You are using an outdated browser. <a href="http://browsehappy.com/">Upgrade your browser today</a> or <a href="http://www.google.com/chromeframe/?redirect=true">install Google Chrome Frame</a> to better experience this site.</p>
    <![endif]-->
    <div id="wrapper">
      <!--PAGE HEADER ******************************************************************* -->
      <header>
        {block:IfHeaderImage}
          <div id="logo"><a href="/"><img src="{image:Header}" alt="{Title}"/></a></div>
        {/block:IfHeaderImage}
        {block:IfNotHeaderImage}
          <h1><a href="/">{Title}</a></h1>
        {/block:IfNotHeaderImage}
        {block:Description}
          <p id="description">{Description}</p>
        {/block:Description}
        <nav>
          <ul>
            {block:HasPages}
            {block:Pages}
            <li><a href="{URL}">{Label}</a></li>
            {/block:Pages}
            {/block:HasPages}
            {block:AskEnabled}
            <li><a href="/ask">{AskLabel}</a></li>
            {/block:AskEnabled}
            {block:SubmissionsEnabled}
            <li><a href="/submit">{SubmitLabel}</a></li>
            {/block:SubmissionsEnabled}
            {block:IfShowArchive}
            <li><a href="/archive">{lang:Archive}</a></li>
            {/block:IfShowArchive}
            {block:IfShowRSS}
            <li><a href="{RSS}">{lang:RSS}</a></li>
            {/block:IfShowRSS}
          </ul>
          {block:IfShowSearch}
          <form action="/search" method="get" class="search">
            <input type="text" name="q" placeholder="{lang:Search}">
          </form>
          {/block:IfShowSearch}
        </nav>
        {block:DayPage}
          <h2>{Month} {DayOfMonth}, {Year}</h2>
        {/block:DayPage}
        {block:TagPage}
          <h2>Posts {lang:Tagged with} "{Tag}"</h2>
        {/block:TagPage}
        {block:SearchPage}
          <h2>{lang:Found SearchResultCount results for SearchQuery}</h2>
        {/block:SearchPage}
        {block:NoSearchResults}
          <h2>{lang:No posts containing SearchQuery}</h2>
        {/block:NoSearchResults}
      </header>
      <!--PAGE LOOP ******************************************************************* -->
      <div id="main" role="main">
        {block:Posts}

        {block:Text}
          <article class="post text">
            {block:Title}
            <header>
              <h2 class="entry-title">{Title}</h2>
            </header>
            {/block:Title}
            <div>
              {Body}
            </div>
        {/block:Text}

        {block:Photo}
          <article class="post photo">
            <figure>
              {LinkOpenTag}
                {block:IfUseHighResPhotos}
                  <img src="{PhotoURL-HighRes}" alt="{PhotoAlt}" />
                {/block:IfUseHighResPhotos}
                {block:IfNotUseHighResPhotos}
                  <img src="{PhotoURL-500}" alt="{PhotoAlt}" />
                {/block:IfNotUseHighResPhotos}
              {LinkCloseTag}

              {block:IfNotUseHighResPhotos}
                {block:HighRes}
                <a class="high-res" href="{PhotoURL-HighRes}">High-Res</a>
                {/block:HighRes}
              {/block:IfNotUseHighResPhotos}

              {block:Caption}
                <figcaption>
                  {Caption}
                </figcaption>
              {/block:Caption}
            </figure>
        {/block:Photo}

        {block:Photoset}
          <article class="post photoset">
            <figure>
              {Photoset-500}
              {block:Caption}
                <figcaption>
                  {Caption}
                </figcaption>
              {/block:Caption}
            </figure>
        {/block:Photoset}

        {block:Quote}
          <article class="post quote">
            <blockquote>{Quote}</blockquote>
            {block:Source}
              <footer>{Source}</footer>
            {/block:Source}
        {/block:Quote}

        {block:Link}
          <article class="post link">
            <header>
              <h2>
                <a href="{URL}" {Target}>{Name}</a>
              </h2>
            </header>
            {block:Description}
            <p> {Description} </p>
            {/block:Description}
        {/block:Link}

        {block:Chat}
        <article class="post chat">
          {block:Title}
          <header>
            <h2>{Title}</h2>
          </header>
          {/block:Title}
          <table>
            {block:Lines}
            <tr>
              <th class="{Alt} {UserNumber}">{block:Label}{Label}{/block:Label}</th>
              <td>{Line}</td>
            </tr>
            {/block:Lines}
          </table>
          {/block:Chat}

        {block:Audio}
          <article class="post audio">
            <header>
              <h2>
                {block:Artist}
                  {Artist}
                {/block:Artist}

                {block:TrackName}
                  {TrackName}
                {/block:TrackName}
              </h2>
            </header>
            <figure>
              {block:AlbumArt}
                <img src="{AlbumArtURL}"/>
              {/block:AlbumArt}

              {block:AudioPlayer}
                {AudioPlayer}
              {/block:AudioPlayer}

              {block:Caption}
                <figcaption>
                  {Caption}
                </figcaption>
              {/block:Caption}
            </figure>
        {/block:Audio}

        {block:Video}
          <article class="post video">
            <figure>
              {Video-500}
              {block:Caption}
                <figcaption>
                  {Caption}
                </figcaption>
              {/block:Caption}
            </figure>
        {/block:Video}

        {block:Answer}
          <article class="post answer">
            <dialog>
              <dt><img src="{AskerPortraitURL-16}"> {lang:Asker asked 2}: </dt>
              <dd>{Question}</dd>

              <dd>{Answer}</dd>
            </dialog>
        {/block:Answer}

            <footer>
              {block:NoteCount}
                <div class="notes"><a href="{Permalink}">{lang:Notes}: {NoteCount}</a></div>
              {/block:NoteCount}
              {block:HasTags}
                <ul>
                  {block:Tags}
                  <li><a href="{TagURL}">#{Tag}</a></li>
                  {/block:Tags}
                </ul>
              {/block:HasTags}

              {block:Date}
              <time datetime="{Year}-{MonthNumberWithZero}-{DayOfMonthWithZero}T{24HourWithZero}:{Minutes}:{Seconds}">
                <a href="{Permalink}">
                  {block:IfUseTimeAgo}
                    {TimeAgo}
                  {/block:IfUseTimeAgo}
                  {block:IfNotUseTimeAgo}
                    {DayOfMonth} {ShortMonth} {Year}
                  {/block:IfNotUseTimeAgo}
                </a>
              </time>
              {/block:Date}

              {block:NoteCount}
                <a href="{Permalink}">{NoteCount}</a>
              {/block:NoteCount}

              {block:PermalinkPage}
                {block:PostNotes}<div>{PostNotes}</div>{/block:PostNotes}
              {/block:PermalinkPage}
            </footer>
          </article>
        {/block:Posts}
      </div>
      <!--PAGE FOOTER ******************************************************************* -->
      <footer>
        {block:PermalinkPagination}
          <nav>
            {block:PreviousPost}<a href="{PreviousPost}">« {lang:Previous}</a>{/block:PreviousPost}
            {block:NextPost}<a href="{NextPost}">{lang:Next} »</a>{/block:NextPost}
          </nav>
        {/block:PermalinkPagination}

        {block:IndexPage}
          {block:Pagination}
            <nav>
              {block:PreviousPage}<a href="{PreviousPage}">« {lang:Newer}</a>{/block:PreviousPage}

              {block:IfUseNumberPagination}
                {block:JumpPagination length="5"}
                    {block:CurrentPage}
                        <span>{PageNumber}</span>
                    {/block:CurrentPage}
                    {block:JumpPage}
                        <a href="{URL}">{PageNumber}</a>
                    {/block:JumpPage}
                {/block:JumpPagination}
              {/block:IfUseNumberPagination}

              {block:NextPage}<a href="{NextPage}">{lang:Older} »</a>{/block:NextPage}
            </nav>
          {/block:Pagination}
        {/block:IndexPage}
        <p>{text:Footer Text}</p>
      </footer>
    </div>
    {block:IfGoogleAnalyticsID}
    <script>
      var _gaq=[['_setAccount','{text:Google Analytics ID}'],['_trackPageview']];
      (function(d,t){var g=d.createElement(t),s=d.getElementsByTagName(t)[0];
        g.src=('https:'==location.protocol?'//ssl':'//www')+'.google-analytics.com/ga.js';
        s.parentNode.insertBefore(g,s)}(document,'script'));
    </script>
    {/block:IfGoogleAnalyticsID}
  </body>
</html>
