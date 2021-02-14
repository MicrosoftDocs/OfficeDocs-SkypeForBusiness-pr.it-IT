---
title: Distribuire il client Skype for Business in Microsoft 365 o Office 365
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Learn how to plan and deploy Skype for Business in small, medium, and large organizations and making it available to your users. '
ms.openlocfilehash: d7c310935c5fa97873183d18b264616404471895
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777241"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a>Distribuire il client Skype for Business in Microsoft 365 o Office 365

Questo articolo spiega le opzioni **[](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** su come tu, l'amministratore, potete distribuire l'app Skype for Business agli utenti dell'organizzazione.
  
Prima di distribuire Skype for Business agli utenti, assicurati di aver eseguito i passaggi da 1 a 3 dell'articolo [Configurare Skype for Business online.](set-up-skype-for-business-online.md) In questo modo, Skype for Business verrà configurato con il tuo dominio, ognuno avrà le proprie licenze e la messaggistica istantanea verrà configurata e configurata la presenza [in Skype for Business online](configure-presence-in-skype-for-business-online.md) per l'organizzazione.
  
> [!NOTE]
> Per installare l'app Skype for Business, gli utenti devono essere amministratori locali del PC o del dispositivo. Oppure dovranno far parte di un gruppo locale in grado di installare app nei propri PC o dispositivi. Se i tuoi utenti non sono autorizzati a installare software nei loro dispositivi, dovrai installare l'app Skype for Business per loro. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>Per la maggior parte delle piccole e medie imprese

 **Istruzioni dettagliate per l'installazione:** Per le piccole e medie imprese, ti consigliamo di chiedere semplicemente agli utenti di installare l'app Skype for Business nel proprio PC. Indica loro queste istruzioni: [Installare Skype for Business.](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb) Se usano mac, fare in modo che puntino alla configurazione di [Lync per Mac 2011 per Office 365.](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88) L'app Skype for Business viene installata separatamente dal resto delle app di Office.
  
 **Microsoft 365 Apps per clienti aziendali:** Se la tua azienda usa un piano Office 365 che include Microsoft 365 Apps per le aziende, ad esempio il piano E3, l'app Skype for Business viene installata allo stesso tempo che gli utenti scaricano e installano Word, Excel, PowerPoint e così via. Questo significa anche che non possono disinstallare Skype for Business a meno che non disinstallino tutto Office.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>Scegliere se rendere Skype for Business disponibile agli utenti

[L'amministratore](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) può scegliere se rendere l'app Skype for Business disponibile agli utenti.
  
- **Per controllare** se il software viene installato da tutti gli utenti dell'azienda: accedi all'interfaccia di amministrazione di Microsoft 365, accedi a Installa **il mio software** e quindi seleziona il software che desideri essere disponibile per gli utenti.
    
    ![Choose the software you want to make available to the people in your company.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- Per controllare se determinate persone dell'azienda ottengono il **software:** accedere all'interfaccia di amministrazione di Microsoft 365, passare a Utenti attivi, selezionare la persona a cui si vuole concedere l'accesso al software, quindi fare clic su Modifica accanto a Licenze di prodotto e attivare o disattivare la   >  licenza.  
    
    ![Choose which software you want the user to access.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Per vedere quali piani sono assegnati agli utenti dell'organizzazione, accedere all'interfaccia di amministrazione di Microsoft 365 >  >  **utenti attivi.** Seleziona la persona nell'elenco e quindi cerca in **Licenze di prodotto.** Se si usa l'interfaccia di amministrazione classica, cercare in **Licenza assegnata.** 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>Distribuzione manuale di Skype for Business agli utenti
<a name="bkmk_manual_1"> </a>

Se desideri che i tuoi utenti installino l'app Skype for Business da una posizione nella rete invece che da Internet, puoi scaricare i file di configurazione. A questo scopo, passare alla **sezione Distribuire manualmente il software utente** dell'interfaccia di amministrazione di Microsoft 365. È quindi possibile selezionare **Installa e** salvare il file exe di installazione in un percorso di rete.
  
Un'altra opzione è scaricare l'app Skype for Business Basic per gli utenti. Puoi scaricare [Microsoft Skype for Business Basic (32 o 64 bit).](https://www.microsoft.com/download/details.aspx?id=49440)
  
Sia per le app Skype for Business base che per quelle complete, dopo aver scaricato i file di configurazione dovrai inviare manualmente (ad esempio, tramite e-mail) il percorso di rete agli utenti per fare in modo che eseguano il programma di configurazione per installare l'app nel computer
  
Puoi anche utilizzare questi download per distribuire l'app Skype for Business agli utenti utilizzando i processi e gli strumenti di distribuzione del software esistente.
  
## <a name="for-larger-and-enterprise-organizations"></a>Per le grandi organizzazioni e le organizzazioni di livello Enterprise

> [!NOTE]
> Questa sezione si applica solo all'app Skype for Business disponibile tramite i piani Office 365. Se la tua organizzazione usa una versione multilicenza dell'app Skype for Business, basata su Windows Installer (MSI), vedi Personalizzare l'installazione client di [Windows in Skype for Business Server.](https://technet.microsoft.com/library/jj204934.aspx)
  
In molte aziende o grandi organizzazioni, gli utenti non sono autorizzati a installare software nel computer. Sono i reparti IT a distribuire il software necessario per i computer degli utenti. Inoltre, i reparti IT potrebbero avere l'esigenza di controllare in che misura si utilizza la larghezza di banda di rete o Internet nell'organizzazione, preferendo quindi installare il software da una posizione vicina nella propria rete anziché da Internet o tramite la rete aziendale.
  
Con Office 365, hai diverse opzioni per distribuire l'app Skype for Business se vuoi controllare da dove viene installata. Alcune di queste opzioni sono:
  
- Scarica l'app Skype for Business nella tua rete locale dall'interfaccia di amministrazione di Microsoft 365, come descritto in Distribuzione manuale di [Skype for Business agli utenti.](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)
    
- Usare lo **[Strumento di distribuzione di Office](https://go.microsoft.com/fwlink/p/?LinkID=626065)** per scaricare Microsoft 365 Apps for Enterprise o l'app Skype for Business nella rete locale. Usare quindi lo Strumento di distribuzione di Office per distribuire l'app agli utenti. Lo Strumento di distribuzione di Office consente di controllare determinati aspetti della distribuzione, ad esempio le lingue e le versioni (32 bit o 64 bit).
    
- Usa i processi e gli strumenti di distribuzione del software esistenti, come Microsoft Endpoint Configuration Manager, per distribuire Microsoft 365 Apps for enterprise o l'app Skype for Business agli utenti. È possibile usare gli strumenti e i processi esistenti con lo Strumento di distribuzione di [Office](https://go.microsoft.com/fwlink/p/?LinkID=626065) o con il software scaricato dall'interfaccia di amministrazione di Microsoft 365.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Altre informazioni sull'utilizzo dello Strumento di distribuzione di Office

Per informazioni dettagliate sul download dello Strumento di distribuzione di Office e per ulteriori informazioni sull'installazione dell'app Skype for Business e di altre app client di Office 365, vedi Gestire le impostazioni di download del [software in Office 365.](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)
  
Ecco una panoramica dei passaggi necessari per usare lo Strumento di distribuzione di Office per distribuire un'app:
  
1. **[Scarica il nuovo Strumento di distribuzione di Office](https://www.microsoft.com/download/details.aspx?id=49117)** dall'Area download Microsoft.
    
2. Crea il file configuration.xml da utilizzare con lo Strumento di distribuzione di Office che dispone delle impostazioni delle app client che desideri, ad esempio impostando la versione (32 bit o 64 bit), la lingua di installazione e così via.
    
3. Usa lo Strumento di distribuzione di Office e il file configuration.xml per scaricare i file di configurazione nella rete interna o locale dalla Rete di distribuzione dei contenuti (CDN) di Office.
    
4. Usa lo Strumento di distribuzione di Office e il file configuration.xml per installare le app client di Office, inclusa l'app Skype for Business.
    
Per informazioni dettagliate sull'utilizzo dello Strumento di distribuzione di Office e sul file configuration.xml, consulta gli articoli seguenti:
  
- [Panoramica dello Strumento di distribuzione di Office](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Impostazioni del file configuration.xml](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>Altre informazioni sull'uso di Microsoft Endpoint Configuration Manager

Puoi utilizzare i processi e gli strumenti di distribuzione del software esistenti, come Microsoft Endpoint Configuration Manager, per distribuire l'app Skype for Business. Questi strumenti e processi possono essere utilizzati con il software scaricato dall'interfaccia di amministrazione di Microsoft 365 o con lo Strumento di distribuzione di Office.
  
Per altre informazioni sull'utilizzo di Configuration Manager per distribuire il software, consulta i seguenti articoli:
  
- [Creare applicazioni in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/create-applications)
    
- [Distribuire le applicazioni con Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
    
Se stai distribuendo l'app Skype for Business come parte della distribuzione di Microsoft 365 Apps per le aziende, vedi [Gestire Microsoft 365 Apps for enterprise con Configuration Manager.](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates)
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Pianificazione degli aggiornamenti per l'app Skype for Business

Nell'ambito della distribuzione dell'app Skype for Business, devi tenere in considerazione in che modo vuoi ottenere gli aggiornamenti dopo l'installazione di Skype for Business. Questi aggiornamenti possono includere nuove funzionalità, aggiornamenti della sicurezza o aggiornamenti non correlati alla sicurezza, ad esempio gli aggiornamenti che offrono miglioramenti a livello di stabilità e prestazioni. I due principali aspetti da prendere in considerazione sono:
  
- Da dove desideri ottenere gli aggiornamenti
    
- La frequenza con cui desideri ottenere gli aggiornamenti delle funzionalità
    
Puoi controllare l'origine degli aggiornamenti e la relativa frequenza ma non puoi scegliere gli specifici aggiornamenti per la sicurezza e non relativi alla sicurezza da scaricare.
  
 **Origine degli aggiornamenti**
  
Per impostazione predefinita, dopo l'installazione dell'app Skype for Business, gli aggiornamenti verranno scaricati automaticamente da Internet non appena sono disponibili da Microsoft. Se desideri avere più controllo sull'origine e sulla frequenza degli aggiornamenti, puoi usare lo Strumento di distribuzione di Office o Criteri di gruppo per eseguire la configurazione.
  
Ad esempio, molte organizzazioni desiderano testare gli aggiornamenti con un gruppo di utenti prima di distribuirli a tutta l'organizzazione. A tale scopo puoi usare lo Strumento di distribuzione di Office o Criteri di gruppo per configurare l'app Skype for Business per ottenere gli aggiornamenti da una posizione specifica nella rete invece di scaricarli automaticamente da Internet. Successivamente, puoi usare lo Strumento di distribuzione di Office per scaricare gli aggiornamenti ogni mese nella rete locale.
  
Per altre informazioni sul funzionamento degli aggiornamenti per il software Office 365, consulta questi articoli:
  
- [Panoramica del processo di aggiornamento per Microsoft 365 Apps for Enterprise](https://technet.microsoft.com/library/dn761709.aspx)
    
- [Scegliere come gestire gli aggiornamenti alle app di Microsoft 365 per le aziende](https://technet.microsoft.com/library/dn761707.aspx)
    
- [Configurare le impostazioni di aggiornamento per Microsoft 365 Apps for Enterprise](https://technet.microsoft.com/library/dn761708.aspx)
    
  **Frequenza di ricezione degli aggiornamenti delle funzionalità**
  
Oltre all'origine degli aggiornamenti, puoi anche controllare la frequenza con la quale ottenere nuove funzionalità per il client Skype for Business. Puoi scegliere se:
  
- Ottenere aggiornamenti delle funzionalità ogni mese, se sono presenti nuove funzionalità
    
- Ottenere aggiornamenti delle funzionalità ogni sei mesi
    
Alcune organizzazioni preferiscono avere il tempo di testare le nuove funzionalità e quindi ottenere gli aggiornamenti solo due volte all'anno invece di ogni mese.
  
È possibile controllare la frequenza con cui si ottengono gli aggiornamenti delle caratteristiche usando lo Strumento di distribuzione di Office o Criteri di gruppo per configurare il canale di aggiornamento. Il Canale mensile offre gli aggiornamenti delle funzionalità mensilmente (all'incirca), mentre Semi-Annual Channel offre aggiornamenti delle funzionalità ogni sei mesi. Per altre informazioni sui canali, vedere Panoramica dei canali di aggiornamento [per Microsoft 365 Apps for Enterprise.](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)
  
## <a name="related-topics"></a>Argomenti correlati

[Configurare Skype for Business online](set-up-skype-for-business-online.md)
  
[Licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
  
 
