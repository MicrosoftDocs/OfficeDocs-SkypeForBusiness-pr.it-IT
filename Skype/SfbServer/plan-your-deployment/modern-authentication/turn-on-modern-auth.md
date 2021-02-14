---
title: Pianificazione della disattivazione dei metodi di autenticazione legacy internamente ed esternamente alla rete
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
description: In questo articolo vengono descritti i cmdlet che consentono agli amministratori di controllare in modo più completo i metodi di autenticazione utilizzati all'interno e all'esterno di un'azienda. Gli amministratori possono attivare o disattivare i metodi di autenticazione internamente o esternamente alla rete.
ms.openlocfilehash: dca7dca332564442110c626a222f7ed5d138efaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810029"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Pianificazione della disattivazione dei metodi di autenticazione legacy internamente ed esternamente alla rete.

> [!NOTE]
> Se si sta per leggere questo articolo, è necessario conoscere le topologie di autenticazione moderna supportate, ADAL e la configurazione dell'autenticazione moderna, ma, in caso contrario, ecco gli articoli necessari per iniziare: 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
L'autenticazione moderna non solo abilita metodi di autenticazione più sicuri, ad esempio l'autenticazione Two-Factor o l'autenticazione basata su certificati, ma può eseguire l'autorizzazione dell'utente senza dover specificare anche un nome utente o una password. È piuttosto utile.

Questo articolo consente di collegare alla rete i buchi che sono stati sfruttati per attacchi Denial Of Service (DOS) su Skype for Business Server, disattivando i metodi meno recenti usati per l'autenticazione, esternamente, internamente o entrambi. Ad esempio, un metodo utile per arrestare gli attacchi DOS è disattivare l'autenticazione integrata di Windows (che include NTLM e Kerberos). La disattivazione di NTLM esternamente e l'utilizzo dell'autenticazione basata su certificato consente di proteggere le password dall'esposizione. Questo perché NTLM utilizza le credenziali della password per autenticare gli utenti, ma l'autenticazione basata su certificato , abilitata dall'autenticazione moderna, non lo fa. Ciò significa che un'opzione ideale per ridurre gli attacchi DOS è bloccare NTLM esternamente e utilizzare solo l'autenticazione basata su certificato.

Bene, iniziamo.

## <a name="what-would-you-be-changing"></a>Cosa cambierebbe? 

Questi cmdlet funzionano sia per i punti di accesso SIP che per i servizi Web. Anche se questi due canali usano metodi di accesso diversi, eseguendo la gamma da NTLM e Kerberos all'accesso anonimo, sono stati presi in considerazione tutti i metodi standard utilizzati da Skype for Business.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Come ottenere i cmdlet Get e Set-CsAuthConfig

Questi cmdlet verranno installati solo dopo l'aggiornamento cumulativo di luglio 2018 (6.0.9319.534) per Microsoft Skype for Business Server 2015 e quindi si dispone di una vasta gamma di topologie che possono essere implementate per il server Skype for Business.

## <a name="topologies"></a>Topologie

È importante tenere presente che si tratta delle topologie supportate coinvolte in questo scenario. Se, ad esempio, è necessario accedere al supporto tecnico per ottenere assistenza per il blocco di un metodo, è necessario disporre di una configurazione tra i tipi seguenti. 

> [!IMPORTANT]
> Nella tabella e nelle descrizioni seguenti, *l'autenticazione* moderna è abbreviata come __MA__ e l'autenticazione integrata *di Windows* è abbreviata in __Win.__ Come promemoria, l'autenticazione integrata di Windows è costituito da due metodi: l'autenticazione NTLM e l'autenticazione Kerberos. È necessario conoscere questa impostazione per leggere correttamente la tabella.


|       |Esternamente  |Internamente  |Parametro  |
|---------|:---------|:---------|---------|
|__Tipo 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Tipo 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__Tipo 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__Tipo 4__   |  MA       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Tipo 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__Tipo 1 Descrizione:__ Questo è lo scenario predefinito quando MA è __attivato__ per Skype for Business Server. In altre parole, questo è il punto *di partenza per* la configurazione di MA.

__Tipo 2 Descrizione:__ Questa topologia blocca *NTLM* esternamente, ma consente il funzionamento interno di NTLM o Kerberos (per i client che non supportano ADAL). Se i client supportano ADAL, utilizzeranno ma internamente.

__Tipo 3 Descrizione:__ Questa topologia richiede ma per tutti gli utenti. Tutti i client che supportano ADAL funzioneranno in questa topologia e le password non verranno sfruttate se, ad esempio, si disattiva l'uso di password con l'autenticazione basata su certificati.

__Tipo 4 Descrizione:__ Questa topologia blocca NTLM *esternamente e* ma internamente. Consente a *tutti i client di* utilizzare internamente i metodi di autenticazione legacy (anche i client che supportano ADAL). 

__Tipo 5 Descrizione:__ esternamente, i client ADAL moderni utilizzeranno MA e tutti i client che non supportano ADAL utilizzeranno i metodi di autenticazione legacy. Tuttavia, *internamente tutti* *i client* utilizzeranno l'autenticazione legacy (inclusi tutti i client che supportano ADAL).

È piuttosto facile perdere la traccia dell'obiettivo di proteggere le password nelle opzioni disponibili. Tieni presente che la situazione ideale è usare MA esternamente (ad esempio, configurando l'autenticazione basata su certificato) per evitare attacchi DOS. Se lo si sfrutta internamente per i client moderni, sarà anche possibile verificare la rete in futuro per quanto riguarda gli attacchi DOS di Skype for Business Server.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Perché usare Set-CsAuthConfig a livello globale

Il cmdlet ha effetto sulla configurazione sia per i ruoli `Set-CsAuthConfig` di registrazione che per i servizi Web.

Questo cmdlet deve essere eseguito a livello globale del server Skype for Business. Può *essere* eseguito a livello di pool, ma non è *consigliabile* perché aggiunge complessità all'installazione. Eseguendo questi comandi a livello di pool, se nel pool non sono inclusi tutti i ruoli (ad esempio, non dispone di servizi Web), le impostazioni verranno impostate solo per il ruolo di registrazione. In tal caso, i servizi Web potranno continuare con le impostazioni del livello Globale, che possono creare confusione nel comportamento (in particolare quando questa operazione viene eseguita involontariamente).

Se un client utilizza le impostazioni di registrazione di un pool e le impostazioni dei servizi Web di un altro pool e le impostazioni di autenticazione sono in uno stato incoerente, è possibile che i client non siano in grado di accedere.

Inoltre, se è presente un solo ruolo per un pool: 
* Set: verranno impostate solo le impostazioni corrispondenti al ruolo esistente. Non verrà visualizzato alcun avviso speciale perché alcune impostazioni *non sono state* impostate. 
* Get- restituirà l'impostazione corrispondente al ruolo esistente e le impostazioni globali per il ruolo inesistente.
* Se nessun ruolo è presente per un pool, sia Set- che Get restituiranno un messaggio di errore.
* Se entrambi i ruoli sono presenti per un pool ma i criteri non sono definiti a livello di pool, get- restituirà un messaggio di errore.

Potrebbe essere più opportuno eseguire un'operazione Get per questi valori e acquisire screenshot o registrare lo stato iniziale prima di apportare eventuali modifiche. È inoltre consigliabile conservare un registro delle modifiche in OneNote.

> [!NOTE]
> 
> Nota: dopo aver configurato CsAuthConfig, è necessario eseguire Enable-CsComputer in ogni computer per avere effetto sulle impostazioni.

> [!IMPORTANT]
> Se si utilizza Lync Web Access (LWA) ed è necessario utilizzare l'accesso basato su moduli (FBA) per l'accesso esterno, riconfigurare LWA in modo che i client possano accedervi con accesso anonimo per supportare questi scenari. Analogamente, se si utilizza pin di accesso esterno, FBA verrà bloccato solo per gli utenti esterni. Se devono modificare il pin, dovranno accedere all'azienda per farlo internamente.

> [!NOTE]
> 
> Se si utilizza il parametro BlockWindowsAuthExternally per bloccare esternamente NTLM, tenere presente che questo blocca anche NTLM internamente per il canale SIP. Tuttavia, i client Skype for Business e Lync più nuovi di 2010 potranno comunque eseguire l'accesso perché utilizzeranno NTLM su HTTP per l'accesso, internamente, e quindi recupereranno un certificato per l'accesso tramite SIP. Tuttavia, i client precedenti al 2010 non saranno in grado di eseguire l'accesso internamente in questa circostanza ed è consigliabile aggiornare queste applicazioni in modo che gli utenti possano riprendere le funzionalità protette.

> [!IMPORTANT] 
> Alcune delle applicazioni Web di Skype for Business non supportano ma. Pertanto, utilizzando lo scenario BlockWindowsAuthExternallyAndInternally, non sarà possibile accedere a queste applicazioni. Le applicazioni senza supporto di Ma sono Utilità di pianificazione Web, Pagina di accesso remoto, Pannello di controllo di Skype for Business (CSCP) e pagina Impostazioni Response Group. 

## <a name="links"></a>Collegamenti 
- Per altre informazioni su PowerShell:
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Per altre informazioni su come usare i comandi o sull'aggiornamento software necessario per installarli:
    - [Briefing dei cmdlet](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Aggiornamenti per Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (generale)
    - Skype [for Business Server 2015 di luglio 2018, Core Components CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


 
