---
title: "Distribuire il client Skype for Business in Office 365"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- httpsfix
- LeftNav_IT_O365
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
description: "Learn how to plan and deploy Skype for Business in small, medium, and large organizations and making it available to your users. "
---

# Distribuire il client Skype for Business in Office 365

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](8c563b81-22c9-4024-9efe-9fe28c7bbc96.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96). 
  
In questo articolo vengono illustrate le opzioni disponibili per l' **[Assegnare ruoli di amministratore in Office 365](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** per distribuire l'app Skype for Business agli utenti dell'organizzazione.
  
Prima di distribuire Skype for Business agli utenti, verificare che avrebbe potuto passaggi da 1 a 3 vedere l'articolo [Configurare Skype for Business online](set-up-skype-for-business-online.md). In questo modo Skype for Business saranno configurati con il proprio dominio, tutti gli utenti avranno le licenze e saranno stati configurati messaggistica Istantanea e [Configurare la presenza in Skype for Business online](configure-presence-in-skype-for-business-online.md) per l'organizzazione.
  
> [!NOTE]
> Per gli utenti installare l'app Skype for Business, è necessario essere amministratori locali sul PC o dispositivo. O occorrerà faccia parte di un gruppo locale che è possibile installare App nei loro PC o dispositivi. Se gli utenti non sono consentiti per installare il software nei propri dispositivi, è necessario installare l'app Skype for Business per loro. 
  
## Per la maggior parte delle piccole e medie imprese

 **Istruzioni dettagliate di installazione:** se hai un'azienda di piccole o medie dimensioni, ti consigliamo di invitare semplicemente i tuoi utenti a installare l'app Skype for Business sui loro PC. Indirizzali alle seguenti istruzioni:[Installare Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb). Se usano il Mac, indirizzali all'argomento [Configurazione di Lync per Mac 2011 per Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88). L'app di Skype for Business è installata separatamente rispetto al resto delle app di Office.
  
 **Clienti di Office 365 Pro Plus:** se la tua azienda utilizza un piano di Office 365 che include Office 365 Pro Plus, ad esempio il piano E3, l'app Skype for Business viene installata nello stesso momento in cui l'utente scarica e installa Word, Excel, PowerPoint e così via. Questo significa anche che l'utente non potrà disinstallare Skype for Business a meno che non disinstalli tutti i prodotti di Office.
  
### Scegliere se rendere Skype for Business disponibile agli utenti

L' [Assegnare ruoli di amministratore in Office 365](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) è possibile scegliere se si desidera rendere disponibili app Skype for Business agli utenti.
  
- **Per controllare se tutti gli utenti della società Ottiene il software**: eseguire l'accesso in a Interfaccia di amministrazione di Office 365, iniziare **l'installazione del software** e quindi selezionare il software di cui si desidera rendere disponibile per gli utenti.
    
    ![Choose the software you want to make available to the people in your company.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **Per controllare se specifiche persone della società ottenere il software**: accedere a Interfaccia di amministrazione di Office 365, passare a **utenti** > **utenti attivi**, selezionare la persona che si desidera concedere l'accesso al software e quindi fare clic su **Modifica** accanto a ** Licenze per i prodotti** e attivare o disattivare le alla licenza.
    
    ![Choose which software you want the user to access.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Se si vuole vedere quali piani assegnati agli utenti dell'organizzazione, accedere a nuovi Interfaccia di amministrazione di Office 365 > **utenti** > **utenti attivi**. Selezionare la persona nell'elenco, quindi individuare la casella di **licenze**. Se si utilizza classica Interfaccia di amministrazione di Office 365, guardare sotto **licenze assegnate**. 
  
### Distribuzione manuale di Skype for Business agli utenti
<a name="bkmk_manual_1"> </a>

Se desideri che i tuoi utenti installino l'app Skype for Business da un percorso di rete invece che da Internet, puoi scaricare i file di configurazione. A tale scopo, passa alla sezione **Distribuire manualmente il software utente** dell'Interfaccia di amministrazione di Office 365. Quindi puoi selezionare **Installa** e salvare il file .exe di installazione in un percorso di rete.
  
In alternativa è possibile scaricare l'app di base Skype for Business per gli utenti. È possibile scaricare [Microsoft Skype for Business Basic (32 o 64 Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=49440).
  
Sia per le app Skype for Business base che per quelle complete, dopo aver scaricato i file di configurazione dovrai inviare manualmente (ad esempio, tramite e-mail) il percorso di rete agli utenti per fare in modo che eseguano il programma di configurazione per installare l'app nel computer
  
Puoi anche utilizzare questi download per distribuire l'app Skype for Business agli utenti utilizzando i processi e gli strumenti di distribuzione del software esistente.
  
## Per le grandi organizzazioni e le organizzazioni di livello Enterprise

> [!NOTE]
>  Questa sezione si applica solo all'app Skype for Business disponibile con i piani Office 365. Se l'organizzazione utilizza una versione multilicenza dell'app Skype for Business basata su Windows Installer (MSI), vedi[Personalizzare l'installazione client in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/jj204934.aspx). 
  
In molte aziende o grandi organizzazioni, gli utenti non sono autorizzati a installare software nel computer. Sono i reparti IT a distribuire il software necessario per i computer degli utenti. Inoltre, i reparti IT potrebbero avere l'esigenza di controllare in che misura si utilizza la larghezza di banda di rete o Internet nell'organizzazione, preferendo quindi installare il software da una posizione vicina nella propria rete anziché da Internet o tramite la rete aziendale.
  
Con Office 365, sono disponibili diverse opzioni per la distribuzione app Skype for Business se si desidera controllare in cui è installato da. Alcune di queste opzioni includono le seguenti:
  
- Scaricare l'app Skype for Business nella rete locale dall'Interfaccia di amministrazione di Office 365, come descritto in [Distribuzione manuale di Skype for Business agli utenti](8c563b81-22c9-4024-9efe-9fe28c7bbc96.md#bkmk_manual).
    
- Usare lo **[Strumento di distribuzione di Office](https://go.microsoft.com/fwlink/p/?LinkID=626065)** per scaricare Office 365 ProPlus o l'app Skype for Business nella rete locale. Successivamente, puoi usare lo Strumento di distribuzione di Office per distribuire l'app agli utenti. Lo Strumento di distribuzione di Office offre la possibilità di controllare alcuni aspetti della distribuzione, ad esempio le lingue e le versioni (32 bit o 64 bit).
    
- Usa i processi e gli strumenti di distribuzione del software, ad esempio System Center Configuration Manager, per distribuire Office 365 ProPlus o l'app Skype for Business agli utenti. Puoi utilizzare i processi e gli strumenti esistenti con lo [Strumento di distribuzione di Office](https://go.microsoft.com/fwlink/p/?LinkID=626065) o con il software che hai scaricato da Interfaccia di amministrazione di Office 365.
    
### Altre informazioni sull'utilizzo dello Strumento di distribuzione di Office

Per informazioni dettagliate sul download dello Strumento di distribuzione di Office e per altre informazioni sull'installazione dell'app Skype for Business e di altre app client di Office 365, consulta [Gestire il software degli utenti in Office 365](https://support.office.com/article/365-c13051e6-f75c-4737-bc0d-7685dcedf360.aspx).
  
Ecco una panoramica dei passaggi previsti dall'uso lo strumento di distribuzione di Office per distribuire un'app:
  
1. **[Scarica il nuovo Strumento di distribuzione di Office](https://go.microsoft.com/fwlink/p/?LinkID=626065)** dall'Area download Microsoft.
    
2. Crea il file configuration.xml da utilizzare con lo Strumento di distribuzione di Office che dispone delle impostazioni delle app client che desideri, ad esempio impostando la versione (32 bit o 64 bit), la lingua di installazione e così via.
    
3. Usa lo Strumento di distribuzione di Office e il file configuration.xml per scaricare i file di configurazione nella rete interna o locale dalla Rete di distribuzione dei contenuti (CDN) di Office.
    
4. Usa lo Strumento di distribuzione di Office e il file configuration.xml per installare le app client di Office, inclusa l'app Skype for Business.
    
Per informazioni dettagliate sull'utilizzo dello Strumento di distribuzione di Office e sul file configuration.xml, consulta gli articoli seguenti:
  
- [Panoramica dello Strumento di distribuzione di Office](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Impostazioni del file configuration.xml](https://technet.microsoft.com/library/jj219426.aspx)
    
### Altre informazioni sull'utilizzo di System Center Configuration Manager

Puoi usare i processi e gli strumenti di distribuzione del software esistenti, ad esempio System Center Configuration Manager, per distribuire l'app Skype for Business. Puoi usare questi processi e strumenti con il software scaricato da Interfaccia di amministrazione di Office 365 o con lo Strumento di distribuzione di Office.
  
Per altre informazioni sull'utilizzo di Configuration Manager per distribuire il software, consulta i seguenti articoli:
  
- [Come creare applicazioni in Configuration Manager](https://technet.microsoft.com/en-us/library/gg682159.aspx)
    
- [Come distribuire le applicazioni in Configuration Manager](https://technet.microsoft.com/en-us/library/gg682082.aspx)
    
Se stai distribuendo l'app Skype for Business all'interno della distribuzione di Office 365 ProPlus, consulta [Distribuire Office 365 ProPlus mediante System Center Configuration Manager](https://technet.microsoft.com/en-us/library/dn708063.aspx).
  
## Pianificazione degli aggiornamenti per l'app Skype for Business

Nell'ambito della distribuzione dell'app Skype for Business, devi tenere in considerazione in che modo vuoi ottenere gli aggiornamenti dopo l'installazione di Skype for Business. Questi aggiornamenti possono includere nuove funzionalità, aggiornamenti della sicurezza o aggiornamenti non correlati alla sicurezza, ad esempio gli aggiornamenti che offrono miglioramenti a livello di stabilità e prestazioni. I due principali aspetti da prendere in considerazione sono:
  
- Da dove desideri ottenere gli aggiornamenti
    
- La frequenza con cui desideri ottenere gli aggiornamenti delle funzionalità
    
Puoi controllare l'origine degli aggiornamenti e la relativa frequenza ma non puoi scegliere gli specifici aggiornamenti per la sicurezza e non relativi alla sicurezza da scaricare.
  
 **Origine degli aggiornamenti**
  
Per impostazione predefinita, dopo l'installazione dell'app Skype for Business, gli aggiornamenti verranno scaricati automaticamente da Internet non appena sono disponibili da Microsoft. Se desideri avere più controllo sull'origine e sulla frequenza degli aggiornamenti, puoi usare lo Strumento di distribuzione di Office o Criteri di gruppo per eseguire la configurazione.
  
Ad esempio, molte organizzazioni desiderano testare gli aggiornamenti con un gruppo di utenti prima di distribuirli a tutta l'organizzazione. A tale scopo puoi usare lo Strumento di distribuzione di Office o Criteri di gruppo per configurare l'app Skype for Business per ottenere gli aggiornamenti da una posizione specifica nella rete invece di scaricarli automaticamente da Internet. Successivamente, puoi usare lo Strumento di distribuzione di Office per scaricare gli aggiornamenti ogni mese nella rete locale.
  
Per altre informazioni sul funzionamento degli aggiornamenti per il software Office 365, consulta questi articoli:
  
- [Panoramica del processo di aggiornamento di Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761709.aspx)
    
- [Scegliere come gestire gli aggiornamenti a Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761707.aspx)
    
- [Configurare le impostazioni di aggiornamento per Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761708.aspx)
    
 **Frequenza di ricezione degli aggiornamenti delle funzionalità**
  
Oltre all'origine degli aggiornamenti, puoi anche controllare la frequenza con la quale ottenere nuove funzionalità per il client Skype for Business. Puoi scegliere se:
  
- Ottenere aggiornamenti delle funzionalità ogni mese, se sono presenti nuove funzionalità
    
- Ottenere aggiornamenti delle funzionalità ogni sei mesi
    
Alcune organizzazioni preferiscono avere il tempo di testare le nuove funzionalità e quindi ottenere gli aggiornamenti solo due volte all'anno invece di ogni mese.
  
Puoi controllare la frequenza degli aggiornamenti delle funzionalità usando lo Strumento di distribuzione di Office o Criteri di gruppo per configurare il canale di aggiornamento. Monthly Channel offre ogni mese (all'incirca) aggiornamenti delle funzionalità, mentre Semi-Annual Channel offre gli aggiornamenti delle funzionalità ogni sei mesi. Per altre informazioni sui canali, consulta [Panoramica dei canali di aggiornamento per Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).
  
## Argomenti correlati

[Configurare Skype for Business online](set-up-skype-for-business-online.md)
  
[Skype for Business e Teams Microsoft componente aggiuntivo per le licenze](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

