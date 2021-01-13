---
title: Pianificazione della disattivazione dei metodi di autenticazione legacy all'interno e all'esterno della rete
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: In questo articolo vengono descritti i cmdlet che conferiscono agli amministratori un maggiore controllo dei metodi di autenticazione utilizzati all'interno e all'esterno di un'azienda. Gli amministratori possono abilitare o disabilitare i metodi di autenticazione internamente o esternamente alla propria rete.
ms.openlocfilehash: dca7dca332564442110c626a222f7ed5d138efaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810029"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Pianificazione della disattivazione dei metodi di autenticazione legacy all'interno e all'esterno della rete.

> [!NOTE]
> Se si sta per leggere questo articolo, è consigliabile conoscere le topologie di autenticazione moderna supportate, ADAL e la configurazione dell'autenticazione moderna, ma, in caso contrario, ecco gli articoli che è necessario avviare: 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
L'autenticazione moderna non consente solo di ottenere metodi di autenticazione più sicuri, come Two-Factor auth o auth basata su certificato, può eseguire l'autorizzazione dell'utente senza che sia necessario un nome utente o una password. È piuttosto comodo.

Questo articolo ti aiuterà a inserire buchi che sono stati sfruttati per attacchi Denial of Service (DOS) su Skype for Business Server, disattivando i metodi più vecchi utilizzati per l'autenticazione, esternamente, internamente o entrambi, alla rete. Ad esempio, un buon metodo che consente di arrestare gli attacchi DOS potrebbe essere quello di disattivare l'autenticazione integrata di Windows (che include NTLM e Kerberos). La disattivazione esterna di NTLM e l'autenticazione basata su certificato consentono di proteggere le password dall'esposizione. Ciò è dovuto al fatto che NTLM utilizza le credenziali delle password per autenticare gli utenti, ma l'autenticazione basata sui certificati, abilitata dalla moderna autenticazione, non lo fa. Questo significa che un'opzione ideale per ridurre gli attacchi DOS consiste nel bloccare l'NTLM esternamente e utilizzare solo l'autenticazione basata su certificati.

Bene, cominciamo.

## <a name="what-would-you-be-changing"></a>Cosa cambierebbe? 

Questi cmdlet funzionano sia per i punti di accesso SIP che per i servizi Web. Anche se questi due canali utilizzano metodi di accesso diversi, eseguendo la gamma da NTLM e Kerberos all'accesso anonimo, sono stati presi in considerazione tutti i metodi standard utilizzati da Skype for business.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Come ottenere i cmdlet Get-e Set-CsAuthConfig

Questi cmdlet verranno installati solo dopo l'aggiornamento cumulativo di luglio 2018 (6.0.9319.534) per Microsoft Skype for Business Server 2015 e quindi si dispone di una vasta gamma di topologie che possono essere implementate per il server Skype for business.

## <a name="topologies"></a>Topologie

È importante tenere presente che queste sono le topologie supportate coinvolte in questo scenario. Se è necessario andare a supporto della Guida per il blocco di un metodo, ad esempio, sarà necessario disporre di una configurazione tra i tipi riportati di seguito. 

> [!IMPORTANT]
> Nella tabella e nelle descrizioni seguenti, *l'autenticazione moderna* è abbreviata come __ma__ e *l'autenticazione integrata di Windows* è abbreviata come __Win__. L'autenticazione integrata di Windows, come promemoria, è costituita da due metodi: NTLM e autenticazione Kerberos. È necessario conoscere questo articolo per leggere correttamente la tabella.


|       |Esternamente  |Internamente  |Parametro  |
|---------|:---------|:---------|---------|
|__Tipo 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Tipo 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__Tipo 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__Tipo 4__   |  MA       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Tipo 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__Descrizione tipo 1:__ Questo è lo scenario predefinito quando MA __è attivato per Skype for business__ server. In altre parole, questo è il *punto di partenza* quando ma è configurato.

__Descrizione tipo 2:__ Questa topologia blocca l'autenticazione NTLM *esternamente*, ma consente l'utilizzo di NTLM o Kerberos (per i client che non supportano adal) all' *interno*. Se i client supportano ADAL, utilizzeranno MA internamente.

__Descrizione tipo 3:__ Questa topologia richiede MA per tutti gli utenti. Tutti i client che supportano ADAL funzioneranno in questa topologia e le password non verranno sfruttate se, ad esempio, si disattiva l'utilizzo di password con l'autenticazione basata su certificato.

__Descrizione tipo 4:__ Questa topologia blocca l'autenticazione NTLM *esternamente* e ma internamente. Consente a *tutti i client* di utilizzare i metodi di autenticazione legacy *internamente* (anche client in grado di adal).

__Descrizione tipo 5:__ *esternamente*, i client di adal moderni utilizzeranno ma e tutti i client che non supportano adal utilizzeranno i metodi di autenticazione legacy. Tuttavia, *internamente* *tutti i client* utilizzeranno l'autenticazione legacy (inclusi tutti i client compatibili con adal).

È piuttosto semplice perdere la cognizione dell'obiettivo di proteggere le password nelle opzioni disponibili. Tenere presente che la situazione ideale consiste nell'utilizzare MA esternamente (ad esempio, configurando l'autenticazione basata su certificato), per evitare attacchi DOS. Se lo si utilizza internamente per i client moderni, sarà anche possibile utilizzare la rete per gli attacchi DOS di Skype for Business Server.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Perché utilizzare Set-CsAuthConfig a livello globale

La `Set-CsAuthConfig` configurazione degli effetti del cmdlet sia nei ruoli di registrazione che in quelli dei servizi Web.

Questo cmdlet deve essere eseguito a livello globale del server Skype for business. *Può* essere eseguito a livello di pool ma *non è consigliato* perché aggiungerà complessità all'installazione. Eseguendo questi comandi a livello di pool, se nel pool non sono inclusi tutti i ruoli, ad esempio non sono presenti servizi Web, le impostazioni verranno impostate solo per il ruolo di registrazione. In questo caso, i servizi Web continueranno a essere configurati a livello globale, il che può comportare un comportamento confusionario (in particolare quando ciò viene effettuato involontariamente).

Se un client utilizza le impostazioni di registrazione da un pool e le impostazioni dei servizi Web di un altro pool e le impostazioni di autenticazione sono in uno stato incoerente, è possibile che i client non siano in grado di eseguire l'accesso.

Inoltre, se è presente un solo ruolo per un pool: 
* Set-consente di impostare solo le impostazioni che corrispondono al ruolo esistente. Non viene fornito alcun avviso speciale perché alcune impostazioni *non* sono state impostate. 
* Get-restituirà l'impostazione corrispondente al ruolo esistente e le impostazioni globali per il ruolo che non esiste.
* Se non è presente alcun ruolo per un pool, sia set-che Get-restituiranno un messaggio di errore.
* Se entrambi i ruoli sono presenti per un pool, ma i criteri non sono definiti a livello di pool, Get-restituirà un messaggio di errore.

Potrebbe essere più saggio fare un get-for questi valori, nonché screenshot o registrare lo stato iniziale prima di apportare eventuali modifiche. È inoltre possibile tenere presente un registro delle modifiche in OneNote.

> [!NOTE]
> 
> Nota: dopo aver configurato CsAuthConfig, è necessario eseguire Enable-CsComputer su ogni computer per rendere effettive le impostazioni.

> [!IMPORTANT]
> Se si utilizza Lync Web Access (LWA) ed è necessario utilizzare l'accesso basato su moduli (moduli) per l'accesso esterno, riconfigurare LWA in modo che i client possano accedervi con accesso anonimo per supportare tali scenari. Analogamente, se si utilizza il pin di accesso esterno, moduli verrà bloccato solo per gli utenti esterni. Se è necessario modificare il PIN, è necessario effettuare l'accesso alla propria società a tale scopo, internamente.

> [!NOTE]
> 
> Se si utilizza il parametro BlockWindowsAuthExternally per bloccare esternamente NTLM, tenere presente che questo blocca anche l'autenticazione NTLM internamente per il canale SIP. Tuttavia, i client Skype for business e Lync più recenti di 2010 saranno comunque in grado di eseguire l'accesso perché utilizzeranno NTLM su HTTP per SignIn, internamente e quindi recupereranno un certificato per l'accesso tramite SIP. Tuttavia, i client precedenti a 2010 non saranno in grado di eseguire l'accesso interno in questa circostanza e potrebbe essere opportuno prendere in considerazione l'aggiornamento di queste applicazioni in modo che gli utenti possano riprendere le funzionalità sicure.

> [!IMPORTANT] 
> Alcune delle applicazioni Web di Skype for business non supportano MA. In questo modo, utilizzando lo scenario BlockWindowsAuthExternallyAndInternally, non sarà possibile accedere a queste applicazioni. Le applicazioni senza supporto di MA sono utilità di pianificazione Web, pagina di accesso esterno, pannello di controllo di Skype for business (CSCP) e pagina impostazioni Response Group. 

## <a name="links"></a>Collegamenti 
- Per ulteriori informazioni su PowerShell:
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Per ulteriori informazioni su come utilizzare i comandi o su CU necessari per installarli:
    - [Informazioni sui cmdlet](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Aggiornamenti per Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (generale)
    - [Luglio 2018 Skype for Business Server 2015, componenti di base cu](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


 
