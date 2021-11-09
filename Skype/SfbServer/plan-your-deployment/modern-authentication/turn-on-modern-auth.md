---
title: Pianificazione della disattivazione dei metodi di autenticazione legacy internamente ed esternamente alla rete
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: In questo articolo vengono descritti i cmdlet che offrono agli amministratori un maggiore controllo dei metodi di autenticazione utilizzati all'interno e all'esterno di un'azienda. Gli amministratori possono attivare o disattivare i metodi di autenticazione internamente o esternamente alla rete.
ms.openlocfilehash: 845af6891d7da419ffd6fc5a4f663cfc2b61a01a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835064"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Pianificazione della disattivazione dei metodi di autenticazione legacy internamente ed esternamente alla rete.

> [!NOTE]
> Se stai per leggere questo articolo, dovresti già conoscere le topologie di autenticazione moderna supportate, ADAL e la configurazione dell'autenticazione moderna, ma, in caso contrario, ecco gli articoli da iniziare: 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](./topologies-supported.md)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](/skypeforbusiness/manage/authentication/use-adal)
  
L'autenticazione moderna non solo abilita metodi di autenticazione più sicuri, come l'autenticazione di Two-Factor o l'autenticazione basata su certificati, ma può eseguire l'autorizzazione dell'utente senza bisogno di un nome utente o di una password. È molto utile.

Questo articolo consente di collegare alla rete i buchi che sono stati sfruttati per attacchi DoS (Denial Of Service) ai server Skype for Business, disattivando i metodi meno recenti utilizzati per l'autenticazione, esternamente, internamente o entrambi. Ad esempio, un buon metodo per arrestare gli attacchi DOS è disattivare l'autenticazione integrata Windows (che include NTLM e Kerberos). La disattivazione di NTLM esternamente e l'utilizzo dell'autenticazione basata su certificati consente di proteggere le password dall'esposizione. Questo perché NTLM usa le credenziali della password per autenticare gli utenti, ma l'autenticazione basata su certificato , abilitata dall'autenticazione moderna, non lo fa. Ciò significa che un'opzione ideale per ridurre gli attacchi DOS è bloccare NTLM esternamente e utilizzare solo l'autenticazione basata su certificato.

D'accordo, iniziamo.

## <a name="what-would-you-be-changing"></a>Cosa cambierei? 

Questi cmdlet funzionano sia per i punti di accesso SIP che per i servizi Web. Sebbene questi due canali utilizzino metodi di accesso diversi, eseguendo la gamma da NTLM e Kerberos all'accesso anonimo, sono stati presi in considerazione tutti i metodi standard utilizzati da Skype for Business.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Come ottenere i cmdlet Get- e Set-CsAuthConfig

Questi cmdlet verranno installati solo dopo l'aggiornamento cumulativo di luglio 2018 (6.0.9319.534) per Microsoft Skype for Business Server 2015 e quindi si dispone di un'ampia gamma di topologie che possono essere implementate per il server Skype for Business.

## <a name="topologies"></a>Topologie

È importante tenere presente che si tratta delle topologie supportate coinvolte in questo scenario. Se, ad esempio, è necessario accedere a Supporto tecnico per informazioni sul blocco di un metodo, sarà necessario disporre di una configurazione tra i tipi seguenti. 

> [!IMPORTANT]
> Nella tabella e nelle descrizioni seguenti,  *l'autenticazione* moderna è abbreviata come *MA e Windows'autenticazione* integrata è abbreviata come __Win__. Come promemoria, Windows'autenticazione integrata è costituito da due metodi: l'autenticazione NTLM e Kerberos. È necessario sapere questo per leggere correttamente la tabella.


|       |Esternamente  |Internamente  |Parametro  |
|---------|:---------|:---------|---------|
|__Tipo 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Tipo 2__   |  Ma       | MA + Win         | BlockWindowsAuthExternally        |
|__Tipo 3__   |  Ma       | Ma        | BlockWindowsAuthExternallyAndInternally        |
|__Tipo 4__   |  Ma       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Tipo 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__Tipo 1 Descrizione:__ Questo è lo scenario predefinito quando ma è __attivato__ per Skype for Business Server. In altre parole, questo è il punto *di partenza quando* ma è configurato.

__Tipo 2 Descrizione:__ Questa topologia blocca *NTLM* esternamente, ma consente il funzionamento interno di NTLM o Kerberos (per i client che non supportano ADAL). Se i client supportano ADAL, utilizzeranno ma internamente.

__Tipo 3 Descrizione:__ Questa topologia richiede ma per tutti gli utenti. Tutti i client che supportano ADAL funzioneranno in questa topologia e le password non verranno sfruttate se, ad esempio, si disattiva l'utilizzo delle password con l'autenticazione basata su certificato.

__Tipo 4 Descrizione:__ Questa topologia blocca NTLM *internamente* e esternamente. Consente a *tutti i client* di utilizzare internamente i metodi di autenticazione legacy (anche i client che supportano ADAL). 

__Tipo 5 Descrizione:__ esternamente, i client ADAL moderni utilizzeranno MA e tutti i client che non supportano ADAL utilizzeranno i metodi di autenticazione legacy. Tuttavia, *internamente tutti* *i client* utilizzeranno l'autenticazione legacy (inclusi tutti i client che supportano ADAL).

È piuttosto facile perdere traccia dell'obiettivo di proteggere le password nelle opzioni disponibili. Tieni presente che la situazione ideale è usare MA esternamente (ad esempio, configurando l'autenticazione basata su certificato), per evitare attacchi DOS. Se lo si sfrutta internamente per i client moderni, si sarà anche a prova di futuro la rete per quanto riguarda gli Skype for Business Server DOS.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Perché usare Set-CsAuthConfig a livello globale

Il `Set-CsAuthConfig` cmdlet ha effetto sulla configurazione sia sul ruolo registrar che sui servizi Web.

Questo cmdlet deve essere eseguito a livello globale del server Skype for Business server. Può *essere* eseguito a livello di pool, ma non è *consigliabile* perché aggiunge complessità all'installazione. Eseguendo questi comandi a livello di pool, se nel pool non sono inclusi tutti i ruoli( ad esempio, non dispone di servizi Web), le impostazioni verranno impostate solo per il ruolo registrar. In tal caso, i servizi Web verranno continuati con le impostazioni del livello Globale, con un comportamento che può confondere (in particolare quando questa operazione viene eseguita involontariamente).

Se un client utilizza le impostazioni di registrazione di un pool e le impostazioni dei servizi Web di un altro pool e le impostazioni di autenticazione sono in uno stato incoerente, è possibile che i client non siano in grado di accedere.

Inoltre, se è presente un solo ruolo per un pool: 
* Set- imposta solo le impostazioni che corrispondono al ruolo esistente. Non verrà visualizzato alcun avviso speciale perché alcune impostazioni *non sono state* impostate. 
* Get- restituirà l'impostazione corrispondente al ruolo esistente e le impostazioni globali per il ruolo inesistente.
* Se nessuno dei due ruoli è presente per un pool, sia Set- che Get- restituiranno un messaggio di errore.
* Se entrambi i ruoli sono presenti per un pool ma i criteri non sono definiti a livello di pool, Get- restituirà un messaggio di errore.

Potrebbe essere più opportuno eseguire un'operazione Get- per questi valori e screenshot o registrare lo stato iniziale prima di apportare eventuali modifiche. È inoltre consigliabile conservare un registro delle modifiche in un OneNote.

> [!NOTE]
> 
> Nota: dopo aver configurato CsAuthConfig, è necessario eseguire Enable-CsComputer in ogni computer per fare in modo che le impostazioni appartienino effetto.

> [!IMPORTANT]
> Se si utilizza Lync Web Access (LWA) ed è necessario utilizzare LBA (Forms-based Access) per l'accesso esterno, riconfigurare LWA in modo che i client possano accedervi con Accesso anonimo per supportare questi scenari. Allo stesso modo, se si utilizza Pin di accesso esterno, FBA verrà bloccato solo per gli utenti esterni. Se devono modificare il pin, dovranno accedere all'azienda per farlo internamente.

> [!NOTE]
> 
> Se si utilizza il parametro BlockWindowsAuthExternally per bloccare esternamente NTLM, tenere presente che questo blocca anche NTLM internamente per il canale SIP. Tuttavia, i client Skype for Business e Lync più nuovi della versione 2010 potranno comunque eseguire l'accesso perché utilizzeranno NTLM su HTTP per l'accesso, internamente, e quindi recupereranno un certificato per l'accesso tramite SIP. Tuttavia, i client precedenti al 2010 non saranno in grado di eseguire l'accesso internamente in questa circostanza ed è consigliabile aggiornare queste applicazioni in modo che gli utenti possano riprendere la funzionalità protetta.

> [!IMPORTANT] 
> Alcune delle Skype for Business Web non supportano ma. Pertanto, utilizzando lo scenario BlockWindowsAuthExternallyAndInternally, non sarà possibile accedere a queste applicazioni. Le applicazioni senza supporto di Ma sono Utilità di pianificazione Web, Pagina di accesso remoto, Pannello di controllo di Skype for Business (CSCP) e Pagina di Impostazioni Response Group. 

## <a name="links"></a>Collegamenti 
- Per altre informazioni su PowerShell:
    -  [Get-CsAuthConfig](/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Per altre informazioni su come usare i comandi o sul cu necessario per installarli:
    - [Briefing dei cmdlet](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Aggiornamenti per Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (generale)
    - Il mese di luglio [2018 Skype for Business Server 2015, Core Components CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


