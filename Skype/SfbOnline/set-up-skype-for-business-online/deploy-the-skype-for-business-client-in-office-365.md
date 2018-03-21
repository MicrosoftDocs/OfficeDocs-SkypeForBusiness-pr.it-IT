---
title: Distribuire il client Skype for Business in Office 365
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'Learn how to plan and deploy Skype for Business in small, medium, and large organizations and making it available to your users. '
ms.openlocfilehash: 5a3af14d7bf507a50ab7d007a066e3bd42d90c50
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2018
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a>Distribuire il client Skype for Business in Office 365

In questo articolo vengono illustrate le opzioni per come, **[amministrazione](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)**, distribuire Skype per applicazioni aziendali per gli utenti nell'organizzazione.
  
Prima di distribuire Skype for Business per gli utenti, assicurarsi che è stata effettuata passaggi da 1 a 3 nell'articolo [configurare Skype Business online](set-up-skype-for-business-online.md). In questo modo, Skype for Business verrà configurato con il tuo dominio, ognuno avrà le proprie licenze e la messaggistica istantanea e la [Configurare la presenza in Skype for Business online](configure-presence-in-skype-for-business-online.md) saranno configurate per l'azienda.
  
> [!NOTE]
> Per installare l'app Skype for Business, gli utenti devono essere amministratori locali dei relativi PC o dispositivi. In alternativa, devono far parte di un gruppo locale che può installare le app nel proprio PC o dispositivo. Se non sono consentiti agli utenti di installare software nei dispositivi, sarà necessario installare Skype per applicazioni aziendali di essi. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>Per la maggior parte delle piccole e medie imprese

 **Istruzioni dettagliate di installazione:** se hai un'azienda di piccole o medie dimensioni, ti consigliamo di invitare semplicemente i tuoi utenti a installare l'app Skype for Business sui loro PC. Puntino a queste istruzioni: [Installare Skype per le aziende](https://support.office.com/en-us/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb?ui=en-US&rs=en-US&ad=US). Se usano il Mac, indirizzali all'argomento [Configurazione di Lync per Mac 2011 per Office 365](https://support.office.com/en-us/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88?ui=en-US&rs=en-US&ad=US). L'app di Skype for Business è installata separatamente rispetto al resto delle app di Office.
  
 **Clienti di Office 365 Pro Plus:** se la tua azienda utilizza un piano di Office 365 che include Office 365 Pro Plus, ad esempio il piano E3, l'app Skype for Business viene installata nello stesso momento in cui l'utente scarica e installa Word, Excel, PowerPoint e così via. Questo significa anche che l'utente non potrà disinstallare Skype for Business a meno che non disinstalli tutti i prodotti di Office.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>Scegliere se rendere Skype for Business disponibile agli utenti

Come [amministratore](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US) è possibile scegliere se si desidera rendere disponibili agli utenti Skype per applicazioni aziendali.
  
- **Ottiene il software per controllare se tutti gli utenti dell'azienda**: accedere a Office 365 admin center, per **l'installazione del software**e quindi selezionare il software si desidera rendere disponibili per gli utenti.
    
    ![Choose the software you want to make available to the people in your company.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **Per controllare se specifici dell'azienda ottenere il software**: accedere a Office 365 admin center, andare a **utenti** > **utenti attivi**, selezionare la persona che si desidera concedere l'accesso al software e quindi fare clic su **Modifica** accanto a **licenze per i prodotti** e attivare o disattivare i di licenza.
    
    ![Choose which software you want the user to access.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Se si desidera visualizzare i piani assegnati alle persone all'interno dell'organizzazione, l'accesso alla nuova interfaccia di amministrazione di Office 365 > **utenti** > **utenti attivi**. Selezionare la persona nell'elenco, quindi cercare sotto **licenze per i prodotti**. Se si utilizza l'interfaccia di amministrazione di Office 365 classica, cercare in **licenza assegnata**. 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>Distribuzione manuale di Skype for Business agli utenti
<a name="bkmk_manual_1"> </a>

Se desideri che i tuoi utenti installino l'app Skype for Business da un percorso di rete invece che da Internet, puoi scaricare i file di configurazione. A tale scopo, passa alla sezione **Distribuire manualmente il software utente** dell'Interfaccia di amministrazione di Office 365. Quindi puoi selezionare **Installa** e salvare il file .exe di installazione in un percorso di rete.
  
Un'altra opzione è quella di scaricare l'app Skype for Business Basic per gli utenti. È possibile scaricare [Microsoft Skype per Business Basic (a 32 o 64 Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=49440).
  
Sia per le app Skype for Business base che per quelle complete, dopo aver scaricato i file di configurazione dovrai inviare manualmente (ad esempio, tramite e-mail) il percorso di rete agli utenti per fare in modo che eseguano il programma di configurazione per installare l'app nel computer
  
Puoi anche utilizzare questi download per distribuire l'app Skype for Business agli utenti utilizzando i processi e gli strumenti di distribuzione del software esistente.
  
## <a name="for-larger-and-enterprise-organizations"></a>Per le grandi organizzazioni e le organizzazioni di livello Enterprise

> [!NOTE]
> Questa sezione si applica solo all'app Skype for Business disponibile con i piani Office 365. Se l'organizzazione utilizza una versione multilicenza dell'app Skype for Business basata su Windows Installer (MSI), vedi[Personalizzare l'installazione client in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/jj204934.aspx). 
  
In molte aziende o grandi organizzazioni, gli utenti non sono autorizzati a installare software nel computer. Sono i reparti IT a distribuire il software necessario per i computer degli utenti. Inoltre, i reparti IT potrebbero avere l'esigenza di controllare in che misura si utilizza la larghezza di banda di rete o Internet nell'organizzazione, preferendo quindi installare il software da una posizione vicina nella propria rete anziché da Internet o tramite la rete aziendale.
  
Con Office 365, sono disponibili diverse opzioni per la distribuzione Skype per applicazioni aziendali se si desidera controllare in cui è installato da. Alcune di queste opzioni includono:
  
- Scaricare l'app Skype for Business nella rete locale dall'Interfaccia di amministrazione di Office 365, come descritto in [Distribuzione manuale di Skype for Business agli utenti](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1).
    
- Usare lo **[Strumento di distribuzione di Office](https://go.microsoft.com/fwlink/p/?LinkID=626065)** per scaricare Office 365 ProPlus o l'app Skype for Business nella rete locale. Successivamente, puoi usare lo Strumento di distribuzione di Office per distribuire l'app agli utenti. Lo Strumento di distribuzione di Office offre la possibilità di controllare alcuni aspetti della distribuzione, ad esempio le lingue e le versioni (32 bit o 64 bit).
    
- Usa i processi e gli strumenti di distribuzione del software, ad esempio System Center Configuration Manager, per distribuire Office 365 ProPlus o l'app Skype for Business agli utenti. Puoi utilizzare i processi e gli strumenti esistenti con lo [Strumento di distribuzione di Office](https://go.microsoft.com/fwlink/p/?LinkID=626065) o con il software che hai scaricato da Interfaccia di amministrazione di Office 365.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Altre informazioni sull'utilizzo dello Strumento di distribuzione di Office

Per informazioni dettagliate sul download dello Strumento di distribuzione di Office e per altre informazioni sull'installazione dell'app Skype for Business e di altre app client di Office 365, consulta [Gestire il software degli utenti in Office 365](https://support.office.com/en-us/article/c13051e6-f75c-4737-bc0d-7685dcedf360).
  
Ecco una panoramica dei passaggi coinvolti utilizzando lo strumento di distribuzione di Office per distribuire un'app:
  
1. **[Scarica il nuovo Strumento di distribuzione di Office](https://www.microsoft.com/en-us/download/details.aspx?id=49117)** dall'Area download Microsoft.
    
2. Crea il file configuration.xml da utilizzare con lo Strumento di distribuzione di Office che dispone delle impostazioni delle app client che desideri, ad esempio impostando la versione (32 bit o 64 bit), la lingua di installazione e così via.
    
3. Usa lo Strumento di distribuzione di Office e il file configuration.xml per scaricare i file di configurazione nella rete interna o locale dalla Rete di distribuzione dei contenuti (CDN) di Office.
    
4. Usa lo Strumento di distribuzione di Office e il file configuration.xml per installare le app client di Office, inclusa l'app Skype for Business.
    
Per informazioni dettagliate sull'utilizzo dello Strumento di distribuzione di Office e sul file configuration.xml, consulta gli articoli seguenti:
  
- [Panoramica dello Strumento di distribuzione di Office](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Impostazioni del file configuration.xml](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-system-center-configuration-manager"></a>Altre informazioni sull'utilizzo di System Center Configuration Manager

Puoi usare i processi e gli strumenti di distribuzione del software esistenti, ad esempio System Center Configuration Manager, per distribuire l'app Skype for Business. Puoi usare questi processi e strumenti con il software scaricato da Interfaccia di amministrazione di Office 365 o con lo Strumento di distribuzione di Office.
  
Per altre informazioni sull'utilizzo di Configuration Manager per distribuire il software, consulta i seguenti articoli:
  
- [Come creare applicazioni in Configuration Manager](https://technet.microsoft.com/en-us/library/gg682159.aspx)
    
- [Come distribuire le applicazioni in Configuration Manager](https://technet.microsoft.com/en-us/library/gg682082.aspx)
    
Se stai distribuendo l'app Skype for Business all'interno della distribuzione di Office 365 ProPlus, consulta [Distribuire Office 365 ProPlus mediante System Center Configuration Manager](https://technet.microsoft.com/en-us/library/dn708063.aspx).
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Pianificazione degli aggiornamenti per l'app Skype for Business

Nell'ambito della distribuzione dell'app Skype for Business, devi tenere in considerazione in che modo vuoi ottenere gli aggiornamenti dopo l'installazione di Skype for Business. Questi aggiornamenti possono includere nuove funzionalità, aggiornamenti della sicurezza o aggiornamenti non correlati alla sicurezza, ad esempio gli aggiornamenti che offrono miglioramenti a livello di stabilità e prestazioni. I due principali aspetti da prendere in considerazione sono:
  
- Da dove desideri ottenere gli aggiornamenti
    
- La frequenza con cui desideri ottenere gli aggiornamenti delle funzionalità
    
Puoi controllare l'origine degli aggiornamenti e la relativa frequenza ma non puoi scegliere gli specifici aggiornamenti per la sicurezza e non relativi alla sicurezza da scaricare.
  
 **Origine degli aggiornamenti**
  
Per impostazione predefinita, dopo l'installazione dell'app Skype for Business, gli aggiornamenti verranno scaricati automaticamente da Internet non appena sono disponibili da Microsoft. Se desideri avere più controllo sull'origine e sulla frequenza degli aggiornamenti, puoi usare lo Strumento di distribuzione di Office o Criteri di gruppo per eseguire la configurazione.
  
Ad esempio, molte organizzazioni desiderano testare gli aggiornamenti con un gruppo di utenti prima di distribuirli a tutta l'organizzazione. A tale scopo puoi usare lo Strumento di distribuzione di Office o Criteri di gruppo per configurare l'app Skype for Business per ottenere gli aggiornamenti da una posizione specifica nella rete invece di scaricarli automaticamente da Internet. Successivamente, puoi usare lo Strumento di distribuzione di Office per scaricare gli aggiornamenti ogni mese nella rete locale.
  
Per altre informazioni sul funzionamento degli aggiornamenti per il software Office 365, consulta questi articoli:
  
- [Panoramica del processo di aggiornamento di Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761709.aspx)
    
- [Scegliere la modalità di gestione degli aggiornamenti per Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761707.aspx)
    
- [Configurare le impostazioni di aggiornamento per Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761708.aspx)
    
 **Frequenza di ricezione degli aggiornamenti delle funzionalità**
  
Oltre all'origine degli aggiornamenti, puoi anche controllare la frequenza con la quale ottenere nuove funzionalità per il client Skype for Business. Puoi scegliere se:
  
- Ottenere aggiornamenti delle funzionalità ogni mese, se sono presenti nuove funzionalità
    
- Ottenere aggiornamenti delle funzionalità ogni sei mesi
    
Alcune organizzazioni preferiscono avere il tempo di testare le nuove funzionalità e quindi ottenere gli aggiornamenti solo due volte all'anno invece di ogni mese.
  
Puoi controllare la frequenza degli aggiornamenti delle funzionalità usando lo Strumento di distribuzione di Office o Criteri di gruppo per configurare il canale di aggiornamento. Monthly Channel offre ogni mese (all'incirca) aggiornamenti delle funzionalità, mentre Semi-Annual Channel offre gli aggiornamenti delle funzionalità ogni sei mesi. Per altre informazioni sui canali, consulta [Panoramica dei canali di aggiornamento per Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).
  
## <a name="related-topics"></a>See also

[Configurare Skype for Business online](set-up-skype-for-business-online.md)
  
[Licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  

