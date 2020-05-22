---
title: Creare un'app "Portale Intranet" di Teams da un sito o una pagina di SharePoint Online
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
ms.reviewer: vinbel
search.appverid: MET150
description: A partire da una pagina o un sito di SharePoint Online, creare una scheda statica autonoma che può essere usata come portale Intranet per l'organizzazione.
localization_priority: Priority
ms.openlocfilehash: 4777b744d76415f45718cb274f402556e1e28240
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326583"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a>Creare un'app "Portale Intranet" di Teams da un sito o una pagina di SharePoint Online

Eseguire i passaggi descritti in questo articolo per creare un'app autonoma e statica all'interno di Teams che collega al sito Intranet dell'organizzazione.

Verrà creata un'*app personale di Teams* per il sito Intranet di SharePoint, che verrà visualizzata sotto forma di scheda all'interno di Teams. Questa scheda può contenere informazioni importanti per tutti gli utenti di Teams. Si tratta di un modo rapido e pratico per consentire agli utenti di Teams di accedere agli aggiornamenti semplicemente facendo clic su una scheda.

Tenere presente che per il processo illustrato è **necessario usare** una pagina o un sito di SharePoint *moderno*. Questo processo non è disponibile per le pagine o i siti *classici*.

> [!IMPORTANT]
> Assicurarsi che il sideload delle app di Teams sia abilitato per il tenant. A seconda della fase in cui ci si trova nel processo di migrazione del portale di amministrazione di Teams, può essere necessario abilitarlo in Teams > Amministrazione o in Amministrazione > Impostazioni > Servizi e componenti aggiuntivi > Microsoft Teams > App > App esterne, nella versione precedente del portale.

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a>Usare App Studio per creare l'app autonoma di SharePoint Online

Informazioni preliminari:

1. È necessario conoscere l'URL di una pagina o un sito di comunicazione o del team moderno di SharePoint Online.
    - Questi siti avranno sempre */teams/* o */sites/* nel percorso.

2. È necessario conoscere il sottodominio del tenant, che verrà usato nel segnaposto **{{subdomain}}**.

3. In questo articolo si userà **{{siteUrl}}** come segnaposto per l'*URL* del sito o della pagina scelta.
    - *URL di esempio*:   https://contoso.sharepoint.com/teams/Contoso   *o* https://contoso.sharepoint.com/sites/Contoso
4. Inoltre, si userà **{{sitePath}}** per indicare il *percorso* dell'URL, ad esempio /teams/Contoso.
    - *Percorsi di esempio*:   /teams/Contoso   *o* /sites/Contoso

Per iniziare, procedere come segue:

1. Passare allo Store di Teams.

2. Installare o aprire App Studio.

3. Fare clic su **Apri **accanto all'opzione dell'app.

4. Con App Studio aperto, fare clic su **Manifest Editor** (Editor manifesto).

5. Selezionare **Create a new app** (Crea una nuova app).

6. Compilare i dettagli dell'app in **App Details**.

7. Fare clic su **Tabs** (Schede) in Capabilities (Funzionalità).

8. Fare clic su **Add** (Aggiungi) nella sezione Personal Tab (scheda personale).

9. Inserire il nome** **e **un nuovo ID entità univoco**.

10. Inserire **URL del contenuto e URL del sito Web**.

- **URL del contenuto**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}  
- **URL del sito Web**: {{siteUrl}}

    Esempio di **URL del contenuto**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub

11. Passare a **Domains and Permissions** (Domini e autorizzazioni). Verificare che la sezione domini validi contenga il nome del dominio di SharePoint Online.

    Esempio: contoso.sharepoint.com

12. Aggiungere le proprietà di **Single Sign-On** dell'app Web seguenti:

     Esempio: ** ID app AAD**: 00000003-0000-0ff1-ce00-000000000000  **URL risorda**: {{subdomain}}.sharepoint.com

    ![Single Sign-On dell'app Web, con ID e URL.](media/personal-app.png)

13. **Salvare** queste proprietà e quindi passare a **Test and distribute** (Test e distribuzione).

14. Installare l'app per testare personalmente l'applicazione.

> [!IMPORTANT]
> Se non si usa App Studio di Teams, sarà necessario comprimere il file manifest.JSON appena creato, passare all'App Store in Teams e fare clic sul collegamento **Carica un' app personalizzata** nell'angolo in basso a destra dell'App Store. In questo modo, l'app verrà resa disponibile.

15. L'app è ora disponibile come scheda statica da caricare e visualizzare in Teams.

## <a name="test-and-view-your-new-static-tab"></a>Testare e visualizzare la nuova scheda statica

Per visualizzare la nuova scheda sul desktop di Teams, passare ai puntini di sospensione **...**, sul lato sinistro della barra dell'app. Trovare la nuova app, caricarla e testare l'applicazione autonoma in Teams.

Se si vuole rendere disponibile la nuova app in una posizione più in alto nel menu a sinistra, è necessario usare un'impostazione di criteri per l'app. Questa impostazione è disponibile nella sezione di amministrazione del team > criteri app > aggiungere un'applicazione bloccata. Quando si assegnano i criteri a un utente per il test, la modifica viene visualizzata dopo poche ore. Tenendo presente questo aspetto, decidere se l'app dovrebbe comparire non appena possibile per evitare ritardi.

Per visualizzare e testare la nuova app in un dispositivo mobile, aprire il menu dell'app toccando la freccia (**^**) sopra la barra delle schede nella parte inferiore dello schermo. Individuare l'app e accedervi nel dispositivo mobile.

> [!CAUTION]
> Il supporto per dispositivi mobili è attualmente in versione Developer Preview. Per abilitarla, passare a Impostazioni > Informazioni e quindi abilitare la modalità di anteprima per sviluppatori.

## <a name="a-sample-manifestjson-file"></a>File Manifest.JSON di esempio

Il file JSON generato avrà un aspetto simile al seguente.

```JSON'
{

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json",

    "manifestVersion": "1.5",

    "version": "1.0.0",

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873",

    "packageName": "com.contoso.teams.devapp",

    "developer": {

        "name": "Contoso", ''

        "websiteUrl": "https://www.contoso.com",

        "privacyUrl": "https://www.contoso.com/privacy",

        "termsOfUseUrl": "https://www.contoso.com/terms"

    },

    "icons": {

        "color": "color.png",

        "outline": "outline.png"

    },

    "name": {

        "short": "Contoso Intranet", '

        "full": "Intranet Portal for Contoso"

    },

    "des    ription": {

        "short": "Intranet portal for Contoso",

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams"

    },

    "accentColor": "#FFFFFF",

    "staticTabs": [

        {

                     "       nti        Id":       "com    unicat    onSi    eTab",

            "name": "Contoso Net",

            "contentUrl": "https://contoso.sharepoint.com/sites/ContosoNet/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoNet/",

            "websiteUrl": "https://contoso.sharepoint.com/sites/ContosoNet",

            "scopes": [

                "personal"

            ]

        },

        {

            "entityId": "teamSiteTab",

            "name": "Team Contoso",

            "contentUrl": "https://contoso.sharepoint.com/teams/TeamContoso/_layouts/15/teamslogon.aspx?SPFX=true&dest=/teams/TeamContoso/",

            "websiteUrl": "https://contoso.sharepoint.com/teams/TeamContoso",

            "scopes": [

                "personal"

            ]

        }

    ],

    "permissions": [

        "identity",

        "messageTeamMembers"

    ],

    "validDomains": [

        "contoso.sharepoint.com"

    ],

    "webApplicationInfo": {

        "id": "00000003-0000-0ff1-ce00-000000000000",

        "resource": "https://contoso.sharepoint.com"

    }

}
```
