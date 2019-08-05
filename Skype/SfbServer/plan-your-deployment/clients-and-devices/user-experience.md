---
title: Pianificare l'esperienza client di Skype for business 2015 per gli utenti
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: "Riepilogo: informazioni sul nuovo Skype for business e sui passaggi che è possibile eseguire per preparare l'ambiente e gli utenti per l'aggiornamento, indipendentemente dal fatto che si usi Skype for business online, Skype for Business Server 2019, Skype for Business Server 2015, Lync Server 2013 o Lync Server 2010."
ms.openlocfilehash: d5224c628624d6d93d8b3a06cd4c59d246523b1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187871"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>Pianificare l'esperienza client di Skype for business 2015 per gli utenti
 
**Riepilogo:** Informazioni sul nuovo Skype for business e sui passaggi che è possibile eseguire per preparare l'ambiente e gli utenti per l'aggiornamento, indipendentemente dal fatto che si usi Skype for business online, Skype for Business Server 2019, Skype for Business Server 2015, Lync Server 2013 o Lync Server 2010.
  
Il 14 aprile 2015 Office Update per Lync 2013 include la nuova interfaccia utente di Skype for business. Questo aggiornamento consente agli amministratori di controllare l'aspetto del client e scegliere se mantenere l'esperienza client di Lync 2013 o usare l'esperienza client Skype for business migliorata. Il client Skype for business ha effettivamente sostituito il client Lync 2013 e ha aggiunto la possibilità per gli amministratori di scegliere tra l'esperienza client Lync esistente e la nuova esperienza client Skype for business. Per informazioni su questo aggiornamento, vedere il [14 aprile 2015 aggiornamento per Lync 2013 (Skype for business) (KB2889923)](https://support.microsoft.com/en-us/kb/2889923/).
  
Il 12 maggio 2015 sarà disponibile un altro aggiornamento mensile di Office che include il client Skype for business aggiornato. Molti clienti che non hanno applicato l'aggiornamento di aprile preleveranno l'aggiornamento del 12 maggio per Office 2013. Le informazioni contenute in questo argomento consentiranno di preparare l'organizzazione, l'ambiente e gli utenti per l'aggiornamento del client. Per semplificare la transizione per gli utenti e i team di supporto, usare le informazioni in questo argomento per decidere quale esperienza del client si vuole per gli utenti e quindi apportare le modifiche all'ambiente prima di distribuire l'aggiornamento del client nell'organizzazione.
  
- [Quali sono le esperienze client desiderate per gli utenti?](user-experience.md#clientexperience)
    
- [Preparare l'ambiente per il client Skype for business](user-experience.md#usinglync)
    
- [Risorse utili per preparare i team di supporto e gli utenti finali per l'aggiornamento](user-experience.md#support)
    
> [!NOTE]
> L'esperienza client di Lync 2013 non è un'opzione per le versioni client di Skype for business 2016. Prima di provare a configurare l'ambiente client per l'utilizzo del client Lync 2013, verifica che la versione client non inizi con il numero 16; ad esempio: 16.x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>Quali sono le esperienze client desiderate per gli utenti?
<a name="clientexperience"> </a>

Con il nuovo client Skype for business, puoi controllare quale esperienza client riceverai dagli utenti, o Lync o Skype for business. L'esperienza client predefinita varia a seconda che si usi Lync o Skype for business locale o online. Se si usa Skype for business online (Lync Online) oggi con Office 365 ProPlus, Office 365 Business Premium o Office 2013, l'esperienza client Skype for business aggiornata, ispirata dall'aspetto di Skype, sarà l'esperienza utente predefinita. Se oggi si usa Lync Server locale, l'esperienza del client Lync sarà l'impostazione predefinita.
  
Puoi configurare l'esperienza client che gli utenti ottengono usando i criteri client. Un criterio client è un set di impostazioni di configurazione applicate agli utenti quando accedono a Lync o Skype for business.
  
### <a name="skype-for-business-client-experience"></a>Esperienza client di Skype for business

Oltre a tutte le funzionalità di Lync, Skype for business offre nuove funzionalità con controlli semplificati e icone familiari di Skype. Alcune nuove funzionalità di Skype for business sono disponibili solo con la nuova esperienza client Skype for business. Per altre informazioni sulle nuove funzionalità di Skype for business, vedere [individuare Skype for business](https://go.microsoft.com/fwlink/p/?LinkId=528686).
  
### <a name="lync-client-experience"></a>Esperienza client Lync

L'esperienza del client Lync è molto simile a quella dell'esperienza client di Lync 2013 che gli utenti hanno già familiarità, ma ci sono alcune modifiche che è necessario consentire agli utenti di conoscere. Per scoprire le differenze tra l'esperienza client Lync e il client Lync 2013, vedere [perché viene visualizzato Skype for business quando si usa Lync?](https://go.microsoft.com/fwlink/p/?LinkId=544712) e i collegamenti aggiuntivi più avanti in questo argomento.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Preparare l'ambiente per il client Skype for business
<a name="usinglync"> </a>

È necessario eseguire alcune operazioni per preparare l'ambiente per l'aggiornamento del client. Prima di iniziare a apportare le modifiche necessarie per configurare l'esperienza client, devi prima di tutto assicurarti di usare una versione di Skype for Business Server o Lync Server che supporti le impostazioni dei criteri client.
  
Dopo aver confermato che si sta usando una versione di Skype for Business Server o Lync Server che supporta le impostazioni dei criteri per controllare l'esperienza del client, è necessario configurare le impostazioni dei criteri nell'ambiente. I passaggi specifici che è necessario seguire dipendono dalla versione di Skype for Business Server o Lync Server in uso e dal fatto che gli utenti siano in locale o online. 
  
È consigliabile apportare queste modifiche prima che l'aggiornamento del client venga recapitato agli utenti, in modo da poter controllare l'esperienza del client dal primo avvio del client Skype for business. Le tabelle seguenti puntano alla procedura da seguire per configurare l'ambiente per l'esperienza client desiderata per gli utenti.
  
|**Deployment**|**Esperienza client di Skype for business**|**Esperienza client Lync**|
|:-----|:-----|:-----|
|Skype for business online  <br/> |Non sono disponibili ulteriori passaggi per distribuire client Build 4711,1002 (aprile, 2015) o versioni successive.  <br/> |[Usare l'esperienza client di Lync con Skype for business online](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |Non sono disponibili ulteriori passaggi per distribuire client Build 4711,1002 (aprile, 2015) o versioni successive.  <br/> |[Usare l'esperienza client Lync con Skype for Business Server locale](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 e Lync Server 2010  <br/> |[Usare l'esperienza client Skype con Lync Server 2013 o Lync Server 2010 locale](user-experience.md#SkypewithLynconprem) <br/> |[Usare l'esperienza client Lync con Lync Server 2013 o Lync Server 2010 locale](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Usare l'esperienza client Skype con Lync Server 2013 o Lync Server 2010 locale
<a name="SkypewithLynconprem"> </a>

Seguire i passaggi descritti in questa sezione se si vuole configurare l'esperienza client Skype in una distribuzione locale. L'esperienza predefinita per l'ambiente locale
  
 **Passaggio 1:** Prima di tutto, verificare che sia in esecuzione una versione di Lync Server che supporti le impostazioni dei criteri client.
  
- **Lync server 2013** : è necessario eseguire l'aggiornamento cumulativo di dicembre 2014 (5.0.8308.857) per lync Server 2013 o un aggiornamento successivo. Per informazioni, vedere [aggiornamenti per Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync server 2010** -è necessario eseguire l'aggiornamento cumulativo di febbraio 2015 (4.0.7577.710) per lync Server 2010 o un aggiornamento successivo. Per informazioni, vedere [aggiornamenti per Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
  **Passaggio 2:** USA quindi un criterio client per impostare l'esperienza del client Skype con il client Skype for business. Sono disponibili **tre opzioni** per l'uso di un criterio client per impostare l'esperienza client.
  
  **Opzione 1:** Impostare l'esperienza client Skype usando un criterio globale. Tieni presente che il criterio globale si applica a tutti gli utenti della distribuzione, ma i criteri per gli utenti e i livelli di sito hanno la precedenza sui criteri globali:
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **Opzione 2:** Modificare un criterio client esistente in uso nell'ambiente per includere l'impostazione per abilitare l'esperienza del client Skype. In questo modo è possibile assegnare l'esperienza client Skype solo agli utenti con i criteri esistenti assegnati:
  
```
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **Opzione 3:** Creare un nuovo criterio da assegnare agli utenti che includono l'impostazione per l'esperienza del client Skype. Prima di tutto, crea il nuovo criterio client e fornisci il nome del criterio come valore del parametro **Identity** :
  
```
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

Assegna quindi il criterio agli utenti, usando il nome del criterio (il valore usato per il parametro **Identity** ) come valore del parametro PolicyName: ****
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **Passaggio 3:** Dopo aver configurato i criteri client, distribuire il client Skype for business, Build 4711,1002 (aprile, 2015) o versioni successive.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Usare l'esperienza client Lync con Lync Server 2013 o Lync Server 2010 locale
<a name="LyncwithLynconprem"> </a>

Questa è l'esperienza predefinita quando il client Skype for business viene distribuito in una distribuzione locale di Lync Server. Non è necessario configurare i criteri client per l'utilizzo dell'esperienza client Lync, ma è consigliabile controllare il comportamento di primo esecuzione per il client. Per impostazione predefinita, la prima volta che gli utenti avviano il client Skype for business, viene usata l'esperienza client Skype e viene visualizzata una notifica agli utenti che richiede di riavviare il client per ottenere l'esperienza del client Lync. È possibile configurare l'ambiente in modo che l'esperienza del client Lync venga visualizzata la prima volta che gli utenti avviano il client, nonché disattivare l'esercitazione del client modificando il registro di sistema nei computer client. Per i passaggi che è necessario eseguire prima di distribuire il client Skype for business, vedere uno degli argomenti seguenti:
  
- **Lync server 2013**, vedere [configurare l'esperienza client con Skype for business in Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync server 2010** vedere [configurare l'esperienza client con Skype for business in Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Usare l'esperienza client Lync con Skype for Business Server locale
<a name="LyncwithSfBServer"> </a>

Seguire i passaggi descritti in questa sezione se si vuole configurare l'esperienza client Lync in una distribuzione di Skype for Business Server locale.
  
Seguire i passaggi descritti in questa sezione se si vuole configurare l'esperienza client Skype in una distribuzione locale. L'esperienza predefinita per l'ambiente locale
  
 **Passaggio 1:** Prima di tutto, distribuire Skype for Business Server.
  
 **Passaggio 2:** USA quindi un criterio client per impostare l'esperienza del client Lync con il client Skype for business. Sono disponibili **tre opzioni** per l'uso di un criterio client per impostare l'esperienza client.
  
 **Opzione 1:** Impostare l'esperienza del client Lync usando un criterio globale. Tieni presente che il criterio globale si applica a tutti gli utenti della distribuzione, ma i criteri per gli utenti e i livelli di sito hanno la precedenza sui criteri globali:
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **Opzione 2:** Modificare un criterio client esistente in uso nell'ambiente per includere l'impostazione per abilitare l'esperienza del client Lync. In questo modo è possibile assegnare l'esperienza client Lync solo agli utenti a cui è assegnato il criterio esistente:
  
```
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **Opzione 3:** Creare un nuovo criterio da assegnare agli utenti che includono l'impostazione per l'esperienza del client Lync. Prima di tutto, crea il nuovo criterio client e fornisci il nome del criterio come valore del parametro **Identity** :
  
```
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

Assegna quindi il criterio agli utenti, usando il nome del criterio (il valore usato per il parametro **Identity** ) come valore del parametro PolicyName: ****
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **Passaggio 3: facoltativo** -per impostazione predefinita, la prima volta che gli utenti avviano il client Skype for business, viene usata l'esperienza client Skype e viene visualizzata una notifica agli utenti che chiedono di riavviare il client per ottenere l'esperienza del client Lync. È possibile configurare l'ambiente in modo che l'esperienza del client Lync venga visualizzata la prima volta che gli utenti avviano il client, oltre a disattivare l'esercitazione del client, modificando il registro di sistema nei computer client. Per i passaggi che è necessario eseguire prima di distribuire il client Skype for business, vedere [configurare l'esperienza client con Skype for business](../../deploy/deploy-clients/configure-the-client-experience.md).
  
 **Passaggio 4:** Dopo aver configurato i criteri client, distribuire il client Skype for business, Build 4711,1002 (aprile, 2015) o versioni successive.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Usare l'esperienza client di Lync con Skype for business online
<a name="LyncwithSfBO"> </a>

Seguire i passaggi descritti in questa sezione se si vuole configurare l'esperienza client Lync e si usa Skype for business online.
  
Se si usa Skype for business online, è comunque possibile usare l'esperienza client di Lync con il client Skype for business nell'organizzazione usando PowerShell remoto per configurare i criteri client. Sono disponibili **tre opzioni** per l'uso di un criterio client per impostare l'esperienza client. Tieni presente che i criteri e i nomi dei parametri sono diversi dalle impostazioni che usi per configurare l'esperienza del client quando usi Skype for business o Lync Server locale.
  
 **Opzione 1:** Impostare l'esperienza del client Lync usando un criterio globale. Tieni presente che i criteri client e sito applicati agli utenti avranno la precedenza su un criterio globale.
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opzione 2:** Modificare un criterio client esistente in uso nell'ambiente per includere l'impostazione per abilitare l'esperienza del client Lync. In questo modo è possibile assegnare l'esperienza client Lync solo agli utenti a cui è assegnato il criterio esistente:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opzione 3:** Usa un'istanza di criteri personalizzata che include l'impostazione per l'esperienza del client Lync.
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Dopo aver configurato i criteri client, distribuire il client Skype for business, Build 4711,1002 (aprile, 2015) o versioni successive.
  
Per informazioni dettagliate su come configurare l'esperienza client con Skype for business online, inclusi i passaggi su come controllare la prima esperienza di esecuzione e gli script di PowerShell che è possibile usare per configurare l'ambiente, vedere [passaggio tra le Skype for business e le interfacce utente del client Lync](https://aka.ms/SfBOUI).
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Risorse utili per preparare i team di supporto e gli utenti finali per l'aggiornamento
<a name="support"> </a>

Per rendere più semplice l'organizzazione e la preparazione della transizione, sono disponibili molte risorse aggiuntive per pianificare, educare e coinvolgere gli utenti finali.
  
- [Video: Introduzione a Skype for business](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Guide introduttive di Skype for business (download)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync è ora Skype for business: Ecco le novità](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype for business: Guida dettagliata per i nuovi utenti](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Perché viene visualizzato Skype for business quando si usa Lync?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

