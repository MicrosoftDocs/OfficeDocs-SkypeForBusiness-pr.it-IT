---
title: Procedure consigliate per la sicurezza di Teams per la messaggistica più sicura
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 11/10/2021
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Un riferimento rapido su come usare Teams in modo sicuro, questo articolo funge da base per le procedure consigliate di sicurezza generali e suggerimenti per la formazione degli utenti sulla messaggistica sicura.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61ba1607f2999ef56c3176d4ba8ed0aaebb82e50
ms.sourcegitcommit: 115e44f33fc7993f6eb1bc781f83eb02a506e29b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2021
ms.locfileid: "60909681"
---
# <a name="security-best-practices-for-microsoft-teams"></a>Procedure consigliate per la sicurezza per Microsoft Teams

La collaborazione tramite messaggistica istantanea e videoconferenze ha consentito a molti settori e istituti di istruzione di continuare a lavorare durante la pandemia. Tuttavia, la collaborazione online in tempo reale su larga scala comporta anche *rischi* da affrontare. In caso contrario, i malinti sfruttano questo cambiamento nel lavoro e nella vita con **campagne di phishing** e **spam.** L'elenco di riferimento numerato in questo articolo funge da base per la sicurezza generale quando si usa Teams per inviare messaggi ad altri utenti ed è materiale sussidiario per la formazione per gli utenti che non hanno esperienza con Teams o per qualsiasi sicurezza e messaggistica istantanea.

Gli stessi rischi di phishing presenti nella posta elettronica esistono nelle app di messaggistica istantanea e collaborazione, quindi è necessario applicare le stesse informazioni e indicazioni agli utenti per proteggere gli utenti di Teams.

A livello di utente, alcune misure possono essere semplici e gli utenti dovrebbero avere la possibilità di basarsi su di esse. Gli utenti non devono ’ fare clic per aprire i collegamenti da chiunque non conoscano o di cui non possono verificare ’ l'identità in base all'articolo [Proteggersi dal phishing](https://support.microsoft.com/en-us/windows/protect-yourself-from-phishing-0c7ea947-ba98-3bd9-7184-430e1f860a44). E per proteggersi da attacchi esterni, gli amministratori tenant possono disabilitare o disattivare la federazione aziendale e l'interoperabilità di Teams for Life (TFL) e Skype, per quanto riguarda [Gestire l'accesso esterno (federazione) - Microsoft Teams | Microsoft Docs](/microsoftteams/manage-external-access).

Il set di funzionalità di collaborazione di Teams consente la messaggistica, la collaborazione sui file, le riunioni, le lavagne e molte altre opportunità di connessione. Queste funzionalità funzionano in Teams for Enterprise, Teams for Life, Skype, Skype for Business, Servizi di comunicazione di Azure (ACS) e altro ancora. Questo significa anche che è necessario proteggere se stessi, i colleghi e i clienti in tutta l'ampiezza di queste funzionalità. Anche in questo caso, ogni utente deve avere la possibilità di prendere la decisione più sicura per se stesso, per i propri pari e per i propri clienti.

## <a name="just-as-with-email-online-safety-must-be-practiced-in-microsoft-teams-messaging"></a>Come per la posta elettronica, la sicurezza online deve essere praticata nella messaggistica di Microsoft Teams

Le misure di sicurezza standard dovrebbero essere ingrati mentre si lavora in Teams.

1. Prestare attenzione ai contatti e alle convocazioni di riunione dall'esterno dell'organizzazione. I noni possono essere significativi. E alcuni possono in segreto significare danni.
2. Se non si ’ riconosce il mittente, è possibile controllare l'identità dell'utente nell'elenco indirizzi globale noto dell'azienda e inoltrare le comunicazioni che non è possibile ’ verificare a un livello superiore per la gestione. In dubbi, non interagire con utenti sconosciuti e non verificati.
3. Se si riceve un collegamento o un file da una persona sconosciuta, non fare clic su di esso. Anche in questo caso, usare la migliore valutazione per conto proprio e la sicurezza di altri utenti, nonché dei clienti.
4. Se la navigazione con un collegamento con clic viene visualizzata in una pagina di collegamenti sicuri in cui non è possibile spostarsi, non tentare di aggirare tale pagina (lo stesso vale per qualsiasi allegato che può terminare in rosso e bloccando la pagina allegati sicuri). Se conosci e consideri attendibile il sito di destinazione, segnala il problema a Microsoft e a chi ti ha indirizzato. Tuttavia, esistono molti motivi per aprire una pagina di blocco e prendere in considerazione le contrassegni rosse, invece di limitarsi alla navigazione.
5. Non fornire mai informazioni personali ad alcuna richiesta non richiesta. Si tratta anche di un rischio per la sicurezza personale. I dettagli semplici come il compleanno possono essere sfruttati dagli utenti malintenzionati.
6. Analizza i collegamenti per verificare l'ortografia, le cifre aggiunte o i caratteri insoliti. Potrebbe essere previsto un collegamento a `www.litware.com/strategies/Metricsbreakout.xlsx`, ma l'indirizzo è simile a `www.litwre.com`, `www.litwarecom.com`o anche `www.litwαre.com`. Se non riconosci il collegamento, sii sospetto. L'indirizzo `www.litware.com` non corrisponde a `www.litware2021.com`.

È importante mantenere la propria cautela e non considerare la sicurezza e la sicurezza degli utenti con cui si lavora con cautela o per la concessione. I singoli utenti dovrebbero sempre avere la possibilità di proteggere se stessi, i colleghi e i clienti tramite la verifica prima di affidarsi.

Infine, è anche fondamentale riconoscere che tutti commetteno errori. Gli utenti possono essere soggetti a fare clic in caso di insosabrità, ad esempio, o quando sono stanco. Gli amministratori devono assicurarsi che le risorse per l'escalation dei clic sui collegamenti al problema e di altri eventi imprevisti di sicurezza siano chiaramente note agli utenti dell'organizzazione, in modo che, in caso di errore, l'utente abbia riscontrato problemi e che possano essere intraprese ulteriori azioni di sicurezza.

> [!TIP]
> Controllare la scheda Profilo di qualsiasi contatto di cui non si è ’ sicuri, in particolare se il messaggio di posta elettronica è esterno all'azienda ( ad esempio, un account che termina con *@litware.com* se l'organizzazione non è *Litware*). Un utente può verificare che le persone che non conoscono siano guest di benvenuto in una riunione controllando la scheda profilo per **(GUEST)**. Gli utenti guest sono invitati espressamente a partecipare.