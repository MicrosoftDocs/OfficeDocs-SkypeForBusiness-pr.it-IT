---
title: Creare un'app del portale Intranet di un team da un sito o una pagina di SharePoint Online
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: È possibile usare un sito o una pagina di SharePoint Online esistente e creare una scheda statica autonoma che può essere usata come portale Intranet per l'organizzazione.
localization_priority: Normal
ms.openlocfilehash: 0215a2e1f79627f55bc14c00a099b25d2859b6f9
ms.sourcegitcommit: f0f2fa999c1ca4a1118377c7938a247f79217609
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106633"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a>Creare un'app del portale Intranet di un team da un sito o una pagina di SharePoint Online

Seguire i passaggi di questo articolo per creare un'app autonoma e statica all'interno di team che si collega al sito Intranet per l'organizzazione.

Viene creata un' *app personale teams* del sito Intranet di SharePoint che verrà visualizzata come tabulazione all'interno di teams. Questa scheda può contenere informazioni importanti per tutti gli utenti del team. Si tratta di un modo rapido e comodo per consentire agli utenti di accedere agli aggiornamenti solo con una tabulazione.

Tenere presente che il processo visualizzato **deve usare** un sito o una pagina di SharePoint *moderna* per il lavoro. Questo processo non è disponibile per i siti o le pagine *classiche* .

> [!IMPORTANT]
> Accertarsi che il caricamento laterale delle app team sia abilitato per il tenant. A seconda di dove ci si trova nel processo di migrazione del portale di amministrazione di teams, potrebbe essere necessario abilitarlo in teams > admin o in amministrazione > impostazioni > servizi e componenti aggiuntivi > Microsoft teams > app > app esterne, nella versione precedente del portale. 

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a>Usare App Studio per creare l'app autonoma di SharePoint Online
''' Prima di iniziare:
1. È necessario conoscere l'URL di un sito del team o di una comunicazione moderna di SharePoint Online o di una pagina.
    - Questi siti avranno sempre */Teams/)* o */sites/* nei percorsi.

2. È necessario conoscere il sottodominio del tenant, che verrà usato nel segnaposto **{{subdomain}}**.

3. Questo articolo userà il segnaposto **{{SiteUrl}}** per l' *URL* del sito o della pagina che hai scelto.
    - *URL*di esempio https://contoso.sharepoint.com/teams/Contoso: *oppure*   https://contoso.sharepoint.com/sites/Contoso 
4. Inoltre, **{{sitePath}}** verrà usato per indicare il *percorso* dell'URL (es:/teams/contoso).
    - *Percorsi*di esempio:/teams/Contoso *o* /sites/contoso 

Iniziare seguendo la procedura seguente:

1. Accedere allo store teams.

2. Installare o aprire App Studio.

3. Fare clic su **Apri**, accanto all'opzione app.

4. Con App Studio aperto, fare clic su **editor manifesto**.

5. **Creare una nuova app**.

6. Compilare tutti i **Dettagli dell'app**.

7. Fare clic su **schede** in funzionalità.

8. Fare clic su **Aggiungi** in scheda personale.

9. Immettere il **nome** e scegliere **un nuovo ID entità univoco**.

10. Inserire il **contenturl e l'URL del sito Web**. 

- **contentUrl**: {{SiteUrl}}/_layouts/15/teamslogon.aspx? SPFX = true&dest = {{sitePath}}  
- **web'iteUrl**: {{siteurl}}'' esempio **contenturl**:https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub 

11. Passare a **Domains e Permissi'ns**. Verificare che la sezione domini validi contenga il nome di dominio di SharePoint Online.
'' Esempio: contoso.sharepoint.com

12. Aggiungere le seguenti proprietà **Single Sign-on per** l'app Web:'' esempio:''''' **ID applicazione AAD**: **URL della risorsa**00000003-0000-0FF1-CE00-000000000000: {{subdomain}}. SharePoint. ![com '''''' web app Single Sign-on, con ID e URL.](media/personal-app.png)

13. **Salvare** queste proprietà e quindi passare a **test e Distribuisci**. 

14. Installa l'app per testare personalmente l'applicazione.

> [!IMPORTANT]
> Se non usi teams App Studio, dovrai. zippare il manifesto. File JSON appena creato, passare all'App Store in teams e fare clic su **upload Custom app** link (nell'angolo in basso a destra dell'app Store). In questo modo l'app potrà essere disponibile.

15. Ora l'app è disponibile come scheda statica da caricare e visualizzare in teams.

## <a name="test-and-view-your-new-static-tab"></a>Testare e visualizzare la nuova scheda statica

Per visualizzare la nuova scheda del desktop teams, passare ai puntini di sospensione (**...**) sul lato sinistro della barra dell'app. Trova la tua nuova app, caricala e prova l'applicazione autonoma in teams.

Se vuoi rendere disponibile la nuova app nel menu a sinistra in una posizione più alta, devi usare un'impostazione di criteri per le app. Questa impostazione è disponibile nella sezione amministrazione del team > criteri delle app > aggiungere un'applicazione bloccata. Quando si assegna il criterio a un utente per il test, la modifica verrà visualizzata 24 ore più tardi. Tenendo presente questo aspetto, decidi dove inserire l'app prima di tutto per evitare ritardi.

Per visualizzare e testare la nuova app in un dispositivo mobile, aprire il cassetto dell'app toccando la freccia (**^**) sopra la barra delle schede nella parte inferiore dello schermo. Trova la tua app e passala nel dispositivo mobile.
        
> [!CAUTION]
> Il supporto per dispositivi mobili è attualmente in anteprima per sviluppatori. Per abilitare l'anteprima dello sviluppatore, passare a impostazioni > informazioni e quindi abilitare la modalità anteprima sviluppatore.

## <a name="a-sample-manifestjson-file"></a>File manifest. JSON di esempio

Il file OCS che si genera avrà un aspetto simile al seguente.

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
''
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