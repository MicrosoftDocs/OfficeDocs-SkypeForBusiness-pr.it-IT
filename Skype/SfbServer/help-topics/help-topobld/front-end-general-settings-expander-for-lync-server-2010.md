---
title: Espansione delle impostazioni generali di Front End per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 'Modificare le proprietà del server front-end o del pool Front-End modificando o configurando gli attributi seguenti. La pagina di configurazione è suddivisa nelle sezioni seguenti:'
ms.openlocfilehash: 1e7fa730745c3eab20288b5b4bfbb9c0d781be83
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697291"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Espansione delle impostazioni generali di Front End per Lync Server 2010

Modificare le proprietà del server front-end o del pool Front-End modificando o configurando gli attributi seguenti. La pagina di configurazione è suddivisa nelle sezioni seguenti:

 **Generale**

- **FQDN**: il nome di dominio completo del server front-end o del pool Front-end.

- Selezionare **Usa tutti gli indirizzi IP configurati** per usare tutti gli indirizzi configurati nel server front-end o nel pool Front-end.

    > [!IMPORTANT]
    > Non selezionare questa opzione se si colloca il Mediation Server nel server front-end o nel pool Front-end. I server di mediazione e i server front-end richiedono indirizzi IP dedicati su cui comunicare.

- Selezionare **limita l'utilizzo del servizio agli indirizzi IP selezionati** e immettere l'indirizzo IP per l' **indirizzo IP principale** per la comunicazione del server front-end o del pool Front-end con il resto della distribuzione. Digitare nell' **indirizzo IP PSTN** l'indirizzo IP associato al Mediation Server.

    **Caratteristiche e funzionalità**

- Servizi di **conferenza**: selezionare la casella di controllo se si vogliono le funzionalità di conferenza nella distribuzione. I servizi di conferenza includono audio, video, condivisione applicazioni, condivisione desktop e conferenze Web. Sarà necessario creare e associare un server di Office Web Apps per le conferenze Web (definito più avanti in questa pagina delle proprietà).

- Se è stata selezionata l'opzione conferenza, è possibile selezionare conferenze telefoniche **con accesso esterno (PSTN)** . Selezionare la casella di controllo per abilitare le caratteristiche dei servizi di conferenza telefonica con accesso esterno.

- Selezionare la casella di controllo VoIP **aziendale** se si intende distribuire le caratteristiche per consentire a Lync Server 2013 di fungere da sistema telefonico vocale usando le tecnologie Voice over IP. includendo l'opzione di distribuzione di telefoni cellulari, trunk SIP o connettività di rete telefonica pubblica commutata tramite Mediation Server, gateway PSTN e IP-PBX, in combinazione o da solo, in base alla progettazione e ai requisiti. Per informazioni dettagliate su Enterprise Voice, vedere [VoIP](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx) aziendale e [piano per VoIP aziendale in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

    **Associazioni**

- **SQL Server Store**: il nome di dominio completo di SQL Server (e facoltativamente un'istanza denominata) associato al server front-end o al pool Front-end. Si seleziona l'archivio di SQL Server dall'elenco o si crea un nuovo archivio di SQL Server facendo clic su **nuovo**

- **Archivio file**: si seleziona il nome di dominio completo del server e la condivisione (nel `\\<FQDN of server>\<share name>`formato) che fungerà da percorso archivio file per i file condivisi creati e usati da Lync Server 2013 per la replica, le directory conferenza e altri scopi. Si seleziona l'archivio file nell'elenco oppure si crea un nuovo archivio di file facendo clic su **nuovo**.

- Selezionare la casella di controllo **Associa server di archiviazione** per abilitare un server di archiviazione per il server front-end o il pool Front-end. Dopo aver selezionato la casella di controllo, selezionare un server di archiviazione esistente nell'elenco o fare clic su **nuovo** per creare le definizioni per un nuovo server di archiviazione.

- Selezionare la casella di **controllo Associa server di monitoraggio** per abilitare un server di monitoraggio per il server front-end o il pool Front-end. Dopo aver selezionato la casella di controllo, selezionare un server di monitoraggio esistente nell'elenco oppure fare clic su **nuovo** per creare le definizioni per un nuovo server di monitoraggio.

- Selezionare la casella di controllo **Associa pool Edge (per i componenti multimediali** per abilitare un server perimetrale per il server front-end o il pool Front-end. Dopo aver selezionato la casella di controllo, selezionare un server perimetrale o un pool esistente nell'elenco oppure fare clic su **nuovo** per creare le definizioni per un nuovo Edge Server o pool.

  **Resilienza**

- Selezionare la casella di controllo **pool Registrar di backup associato** per selezionare dall'elenco un server front-end o un pool Front-end che sarà il registrar, ovvero il front end server o il pool Front-End designato come registrar secondario, se il principale non riesce.

- Se è stato selezionato pool di registrar di backup associato e si è scelto un registrar di backup, è possibile selezionare la casella di controllo per il **failover automatico e il failback per voce**. Ora puoi definire le proprietà numeriche per il **rilevamento del failover vocale interno (sec)** e l' **intervallo di failback vocale (sec)**. Per informazioni dettagliate, vedere [pianificazione della resilienza di Enterprise Voice](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

  **Servizi Web**

- Per configurare i **servizi Web interni**, è possibile definire le **porte di ascolto** per **http** e **https**. Per impostazione predefinita, si tratta rispettivamente della porta TCP 80 e della porta TCP 443. È anche possibile configurare le **porte pubblicate** per **http** e **https**. Per impostazione predefinita, si tratta rispettivamente della porta TCP 80 e della porta TCP 443. In base alla configurazione e all'uso dei servizi Web interni di bilanciamento del carico (bilanciamento del carico hardware e bilanciamento del carico DNS), modificare i valori della porta per definire le porte in attesa e pubblicate.

    > [!IMPORTANT]
    > I servizi Web interni e le porte di ascolto e pubblicazione definite sono per i client e i dispositivi interni. I client e i dispositivi esterni usano i servizi Web esterni per l'ascolto e le porte pubblicate, insieme ai servizi Web esterni definiti Fully Qualified Domain Name (FQDN).

- Per configurare i **servizi Web esterni**, è possibile definire le **porte di ascolto** per **http** e **https**. Per impostazione predefinita, si tratta rispettivamente della porta TCP 80 e della porta TCP 443. È anche possibile configurare le **porte pubblicate** per **http** e **https**. Per impostazione predefinita, si tratta rispettivamente della porta TCP 80 e della porta TCP 443. In base alla configurazione e all'uso dei servizi Web interni di bilanciamento del carico (bilanciamento del carico hardware e bilanciamento del carico DNS), modificare i valori della porta per definire le porte in attesa e pubblicate.

    > [!IMPORTANT]
    > I servizi Web esterni e le porte di ascolto e pubblicazione definite sono per i client e i dispositivi esterni. I client e i dispositivi esterni usano i servizi Web esterni per l'ascolto e le porte pubblicate, in genere definiti dal proxy inverso insieme al nome di dominio completo (FQDN) dei servizi Web esterni definiti. La relazione tra l'FQDN dei servizi Web esterni e gli URL semplici definisce gli indirizzi URL (Uniform Resource Locator) che i client esterni useranno per accedere ai servizi disponibili per utenti e dispositivi esterni. Per altre informazioni sugli URL semplici, vedere [pianificazione di URL semplici](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx).

  **Mediation Server**

- Per configurare le proprietà di **Mediation Server** per un Mediation Server collocato, ovvero un Mediation Server distribuito nel server front-end o nel pool Front End, selezionare **abilitato Mediation Server collocato**.

- Per definire le **porte in ascolto** di un Mediation Server collocato, digitare il valore della porta **TLS** e **TCP** in cui è in ascolto il Mediation Server collocato. Per impostazione predefinita, TLS è definito come porta TCP 5067.

- Per definire un valore di porta TCP per il Mediation Server, selezionare la casella di controllo **Abilita porta TCP** . Per impostazione predefinita, Mediation Server usa il protocollo Transport Layer Security (TLS) su TCP. Le porte TCP sono disponibili solo quando l'abilitazione della selezione della porta TCP è abilitata.

    > [!NOTE]
    > Si tratta di un'impostazione facoltativa e si dovrebbe fare riferimento ai requisiti del gateway o PSTN per determinare se è necessario. Per impostazione predefinita, il valore della porta TCP è 5068.

- Definisci Trunks associati al Mediation Server collocato. Se sono già stati definiti, i trunk potranno essere associati al Mediation Server.

    Se si ha più di un gateway associato a un Mediation Server, è possibile specificare il gateway predefinito selezionando il gateway che si vuole impostare come predefinito e facendo clic su **Imposta come predefinito**. Se si sceglie di rimuovere il gateway predefinito corrente, selezionare il gateway e fare clic su Rimuovi **impostazione predefinita**.

> [!IMPORTANT]
> Se si apportano modifiche alle proprietà in questa finestra di dialogo, è necessario pubblicare la topologia ed eseguire la distribuzione guidata di Skype for Business Server in tutti i server interessati. Dopo la pubblicazione della nuova topologia, viene fornito un elenco dei server interessati in cui è necessario eseguire la distribuzione guidata di Skype for Business Server come collegamento nella schermata Riepilogo pubblicazione topologia. Per informazioni dettagliate sulla pubblicazione della topologia aggiornata, vedere [pubblicare la topologia](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx). Per informazioni dettagliate sulla distribuzione guidata di Skype for Business Server, vedere [strumenti di amministrazione di Lync Server](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx).

Fare clic su **OK** per salvare e confermare le modifiche apportate al documento della topologia.

Fare clic su **Annulla per annullare** le modifiche e chiudere le **proprietà di modifica** per il server front-end o per il pool Front-end.

Fare clic su **Guida** per leggere questo argomento della guida.

## <a name="see-also"></a>Vedere anche

[Definire e configurare un pool Front-end o un server Standard Edition](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)
