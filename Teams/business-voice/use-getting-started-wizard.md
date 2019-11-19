---
title: Usare la procedura guidata Attività iniziali per configurare Business Voice
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8e6ed778af0136516286798b0a7b04602f571de2
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653532"
---
# <a name="use-the-getting-started-wizard-to-set-up-business-voice"></a>Usare la procedura guidata Attività iniziali per configurare Business Voice

La procedura guidata Attività iniziali per Microsoft 365 Business Voice offre un modo semplice e veloce per iniziare a ricevere ed effettuare telefonate in Microsoft Teams. Per le aziende di piccole dimensioni che partono da zero, la procedura guidata consente di iniziare a usare il sistema in pochi minuti con numeri di telefono, menu di chiamata, messaggi di saluto e altro ancora. Per le aziende più grandi con una soluzione di telefonia consolidata, la procedura consente di configurare una distribuzione pilota di Business Voice, in modo da poterlo usare con pochi utenti prima di configurarlo per tutti. In entrambi i casi, si può iniziare a usare Business Voice appena terminata la procedura guidata.

È consigliabile leggere questo articolo prima di avviare la procedura guidata. Quando si è pronti, aprire la procedura guidata selezionando **Inizia** nella pagina [Introduzione a Microsoft 365 Business Voice](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/apps/SmbVoice). Assicurarsi di accedere con l'account usato per creare l'abbonamento o un altro account di amministratore globale.

> [!IMPORTANT]
> Business Voice è attualmente disponibile in Canada e nel Regno Unito. Altri paesi e aree geografiche diventeranno disponibili nel 2020.
>
> Microsoft Teams e Business Voice funzionano solo quando le cassette postali degli utenti si trovano in Microsoft 365.  Le cassette postali ubicate nel server di Exchange locale non sono supportate.

<!-- After you've finished the wizard, here are a couple articles you can check out to see what you can do with Business Voice and learn how to customize it. If you don't want to customize anything, you're done! You can start using Business Voice right away.

* [Things to try with Business Voice](things-to-try.md)
* [Customize Business Voice](customize-business-voice.md)
-->

## <a name="emergency-services-location"></a>Ubicazione dei servizi di emergenza

<table>
    <tr>
        <td>Se si vuole modificare l'indirizzo di emergenza, fare clic su <b>Modifica</b> e immettere un nuovo indirizzo. L'indirizzo specificato viene convalidato per verificare che sia legittimo e formattato correttamente per i servizi di risposta alle emergenze. Se è valido, l'indirizzo viene assegnato a tutti gli utenti a cui si assegnerà un numero nel passaggio successivo. Se si hanno dipendenti in più ubicazioni, l'argomento Personalizzare Business Voice illustra come aggiungere e assegnare più indirizzi di emergenza dopo aver completato la procedura guidata Attività iniziali.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

Per saperne di più, vedere [Che cosa sono il routing delle chiamate, gli indirizzi e le posizioni per gli interventi di emergenza?](../what-are-emergency-locations-addresses-and-call-routing.md)

## <a name="company-phone-number"></a>Numero di telefono aziendale

<table>
    <tr>
        <td>Oltre a configurare un nuovo numero di telefono locale, si può scegliere di acquistare un numero verde o trasferire un numero esistente in Microsoft 365. Se si sceglie di configurare un numero verde, è necessario acquistare un piano per chiamate. Se si vogliono trasferire uno o più numeri in Microsoft 365, è possibile farlo nell'[interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com) al termine della procedura guidata.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> Se si sceglie di trasferire uno o più numeri di telefono esistenti in Microsoft 365, nella procedura guidata verrà comunque visualizzato un numero di telefono temporaneo. Non si tratta di un errore. Dopo aver completato la procedura guidata e completato il processo di portabilità, il numero di telefono temporaneo verrà sostituito con il numero di telefono effettivo.

## <a name="assigning-licenses-to-users"></a>Assegnazione di licenze agli utenti

<table>
    <tr>
        <td>Selezionare le persone dell'organizzazione che vogliono effettuare o ricevere telefonate all'esterno di Teams, ad esempio per chiamare un fornitore. È possibile selezionare un numero di utenti corrispondente al numero di licenze di Business Voice disponibili. Se ne servono di più, è possibile acquistare altre licenze al termine della procedura guidata.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-get-numbers.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> Se si vogliono trasferire i numeri di telefono esistenti in Microsoft 365 per singoli utenti, è possibile farlo al termine della procedura guidata. Dopo aver completato il processo di portabilità, i numeri di telefono trasferiti sostituiranno i numeri di telefono temporanei selezionati dalla procedura guidata.

## <a name="incoming-call-greeting"></a>Messaggio di saluto per le chiamate in arrivo

<table>
    <tr>
        <td>È possibile caricare un file audio (MP3 o WAV) di dimensioni massime di 5 megabyte (MB) da usare come messaggio di saluto, oppure si può digitare il messaggio e Microsoft 365 userà la sintesi vocale per leggerlo ai chiamanti. Il messaggio di saluto sarà la prima cosa che udrà chi chiama il numero di telefono dell'azienda. Potrebbe essere necessario scrivere le parole con ortografia errata o usare grafie fonetiche per ottenere la pronuncia giusta.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-greeting.png" width="400">
        </td>
    </tr>
</table>

## <a name="call-menu-and-forwarding"></a>Menu di chiamata e inoltro di chiamata

<table>
    <tr>
        <td>È possibile inoltrare tutte le chiamate a un utente specifico oppure configurare un menu di chiamata da cui scegliere opzioni. Se si crea un menu di chiamata, è possibile specificare le opzioni che un chiamante può selezionare premendo un numero sul tastierino del telefono o pronunciando l'opzione con un comando vocale. Ogni opzione di menu può essere inoltrata a un utente. <br>
        Si può scegliere di caricare un file audio (MP3 o WAV) fino a un massimo di 5 MB che fornisce istruzioni al chiamante oppure è possibile digitare le istruzioni. Microsoft 365 userà la sintesi vocale per leggere le istruzioni al chiamante. Per ottenere la pronuncia giusta potrebbe essere necessario scrivere le parole così come si pronunciano, usando un'ortografia errata.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-call-forwarding-rules.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> Le attività iniziali guidate consentono di configurare un semplice menu di chiamata per diventare subito operativi. Se si hanno più numeri di telefono con i menu di chiamata da configurare o se si vogliono configurare menu di chiamata più complessi, detti anche operatori automatici, è possibile farlo seguendo la procedura descritta in [Configurare un operatore automatico nel cloud](set-up-auto-attendants.md) al termine della procedura guidata.

<table>
    <tr>
        <td> <p>Nella pagina di<b> </b>panoramica, la procedura guidata Attività iniziali raccoglie tutti i dati inseriti e configura Business Voice. È possibile visualizzare i numeri di telefono assegnati agli utenti, esaminare il menu di chiamata, ascoltare il messaggio di saluto e altro ancora. </p>
             <p>La configurazione di Business Voice richiede alcuni minuti. Si può fare clic su <b>Fatto</b> e la configurazione di Business Voice continuerà in background oppure si può attendere il completamento. Una volta completata la procedura, passare a <b>Voce </b>nell'<a href="https://admin.teams.microsoft.com" target="_blank">interfaccia di amministrazione di Teams</a> per configurare altre funzionalità di Business Voice.</p>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-finish-page.png" width="400">
        </td>
    </tr>
</table>