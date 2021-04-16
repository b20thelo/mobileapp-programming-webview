RAPPORT ASSIGNMENT 2.

I denna uppgift har jag lärt mig flera saker varav några är att byta namn på appen, ge appen
tillgång till internet vilket behövs för att kunna visa webbsidor och sedan att skapa en WebView.
Min WebView skapade jag genom att gå in i resursmappen och där öppna upp laoutfilen och skapa
ett WebView-element. Jag gav WebViewelementet ett id och ändrade så att layouten skulle matcha
parent på både höjd och bredd då jag ville att storleken skulle vara samma som själva appen.

I Mainactivity skapade jag sedan en privat variabel som jag namngav myWebView och sedan i onCreate()
lade jag till min WebView och och anropade WebViewelement jag tidigare skapat i layoutfilen
med hjälp av det id jag gav elementet. Sedan aktiverade jag Javascript så det kan köras.

För att ha något att visa i appen skapa jag en lokal html-sida som jag la i en asset-mapp.
Jag skrev lite vanlig html-kod i den för att ha något att visa och kunna se att den faktiskt visas
när jag sedan kopplade den till menyalternativet "Internal Web Page" och klickade på det.
Jag skapade även en koppling till en extern hemsida där jag valde his.se.

KODSNUTT FRÅN MIN APP.

Här har jag lagt in funktion som läser in en extern och sedan intern hemsida.
```
public void showExternalWebPage(){
        myWebView.loadUrl("https://www.his.se/");
    }
public void showInternalWebPage(){
    myWebView.loadUrl("file:///android_asset/about.html");
}
```
Här har jag lagt in så att funktionerna showExternalWebPage() och showIxternalWebPage() anropas när
man klickar på externa eller  interna hemsidan i menyn.
```
@Override
    public boolean onOptionsItemSelected(MenuItem item) {
        // Handle action bar item clicks here. The action bar will
        // automatically handle clicks on the Home/Up button, so long
        // as you specify a parent activity in AndroidManifest.xml.
        int id = item.getItemId();

        //noinspection SimplifiableIfStatement
        if (id == R.id.action_external_web) {
            Log.d("==>","Will display external web page");
            showExternalWebPage();
            return true;
        }

        if (id == R.id.action_internal_web) {
            Log.d("==>","Will display internal web page");
            showInternalWebPage();
            return true;
        }

        return super.onOptionsItemSelected(item);
    }
```

Med i projektet finns även screenshot tagna med Android virtual device. Filer som visar resultatet
av kodsnuttarna ovan är döpta till:
- App_externalwebpage.png
- App_internalwebpage.png
