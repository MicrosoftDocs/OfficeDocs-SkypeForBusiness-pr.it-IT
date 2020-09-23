---
title: Espansione delle impostazioni generali di Front End Server per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 'È possibile modificare le proprietà del front end server o del pool Front End modificando o configurando gli attributi seguenti. La pagina di configurazione è suddivisa nelle sezioni seguenti:'
ms.openlocfilehash: 6d7cdb9067ff88b383077538e38c39c2f8e86a5a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219097"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Espansione delle impostazioni generali di Front End Server per Lync Server 2010

È possibile modificare le proprietà del front end server o del pool Front End modificando o configurando gli attributi seguenti. La pagina di configurazione è suddivisa nelle sezioni seguenti:

 **Generale**

- **FQDN**: il nome di dominio completo del front end server o del pool Front end.

- Selezionare **Usa tutti gli indirizzi IP configurati** per utilizzare tutti gli indirizzi configurati in front end server o pool Front end.

    > [!IMPORTANT]
    > Non è necessario selezionare questa opzione se si colloca il Mediation Server nel front end server o nel pool Front end. Mediation Server e front end server devono disporre di indirizzi IP dedicati su cui comunicare.

- Selezionare **Limita utilizzo servizio a indirizzi IP selezionati** e immettere l'indirizzo IP per l' **indirizzo IP primario** per il front end server o la comunicazione del pool Front end con il resto della distribuzione. Digitare nell' **indirizzo IP PSTN** l'indirizzo IP associato al Mediation Server.

    **Caratteristiche e funzionalità**

- **Servizio di conferenza**: selezionare la casella di controllo per aggiungere funzionalità di conferenza alla distribuzione. Queste funzionalità includono audio, video, condivisione di applicazioni, condivisione desktop e conferenze Web. Sarà necessario creare e associare un server Office Web Apps per le conferenze Web (definito più avanti in questa pagina delle proprietà).

- Se è stata selezionata l'opzione servizi di conferenza, è possibile selezionare le conferenze telefoniche **con accesso esterno (PSTN)** . Selezionare la casella di controllo per abilitare le funzionalità di conferenza telefonica con accesso esterno.

- Selezionare la casella di controllo VoIP **aziendale** se si intende distribuire le funzionalità per consentire a Lync Server 2013 di fungere da sistema di telefonia vocale utilizzando le tecnologie Voice over IP. tra cui l'opzione di distribuzione di telefoni cellulari, trunk SIP o connettività di rete di telefonia pubblica commutata tramite Mediation Server, gateway PSTN e IP-PBX, in combinazione o da solo, in base alla progettazione e ai requisiti. Per informazioni dettagliate su VoIP aziendale, vedere [VoIP aziendale](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx) e [pianificare VoIP aziendale in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

    **Associazioni**

- **Archivio SQL Server**: il nome di dominio completo di SQL Server e facoltativamente un'istanza denominata associata al front end server o al pool Front end. È possibile selezionare l'archivio SQL Server nell'elenco o crearne uno nuovo facendo clic su **Nuovo**

- **Archivio file**: selezionare il nome di dominio completo del server e la condivisione (nel formato  `\\<FQDN of server>\<share name>` ) che fungerà da percorso archivio file per i file condivisi creati e utilizzati da Lync Server 2013 per la replica, le directory conferenze e altri scopi. È possibile selezionare l'archivio file nell'elenco o crearne uno nuovo facendo clic su **Nuovo**.

- Selezionare la casella di controllo **Associa server di archiviazione** per abilitare un server di archiviazione per il front end server o il pool Front end. Dopo aver selezionato questa casella di controllo, selezionare un server di archiviazione esistente nell'elenco oppure fare clic su **nuovo** per creare le definizioni per un nuovo server di archiviazione.

- Selezionare la casella di controllo **Associa Monitoring Server** per abilitare un Monitoring Server per il front end server o il pool Front end. Dopo aver selezionato questa casella di controllo, selezionare un server di monitoraggio esistente nell'elenco oppure fare clic su **nuovo** per creare le definizioni per un nuovo server di monitoraggio.

- Selezionare la casella di controllo **Associa pool di server perimetrali (per i componenti multimediali** per abilitare un perimetro per questo front end server o per il pool Front end. Dopo aver selezionato la casella di controllo, selezionare un server perimetrale o un pool esistente nell'elenco oppure fare clic su **nuovo** per creare le definizioni per un nuovo server perimetrale o pool.

  **Con resilienza**

- Selezionare la casella di controllo **pool di registrazione di backup associato** per selezionare dall'elenco un front end server o un pool Front end che fungerà da registrazione di backup, ovvero il front end server o il pool Front End designato come registrar secondario nel caso in cui il principale abbia esito negativo.

- Se è stato selezionato pool di registrazione di backup associato e si è scelto un servizio di registrazione di backup, è possibile selezionare la casella di controllo per il **failover e il failback automatici per Voice**. È ora possibile definire le proprietà numeriche per il **rilevamento di failover vocale interno (sec)** e l' **intervallo di failback vocale (sec)**. Per informazioni dettagliate, vedere [Planning for Enterprise Voice resilienza](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

  **Servizi Web**

- Per configurare **Servizi Web interni**, è necessario definire **Porte di attesa** per **HTTP** e **HTTPS**. Le porte predefinite sono rispettivamente la porta TCP 80 e la porta TCP 443. È inoltre necessario configurare **Porte pubblicate** per **HTTP** e **HTTPS**. Le porte predefinite sono rispettivamente la porta TCP 80 e la porta TCP 443. Modificare i valori di queste porte a seconda della configurazione dei servizi Web interni e dell'uso dei servizi di bilanciamento del carico (hardware e DNS).

    > [!IMPORTANT]
    > I servizi Web interni e le porte di attesa e pubblicate definite sono riservate ai client e ai dispositivi interni. I client e i dispositivi esterni usano le porte di attesa e pubblicate dei servizi Web esterni, insieme al nome di dominio completo (FQDN) definito per tali servizi.

- Per configurare **Servizi Web esterni**, è necessario definire **Porte di attesa** per **HTTP** e **HTTPS**. Le porte predefinite sono rispettivamente la porta TCP 80 e la porta TCP 443. È inoltre necessario configurare **Porte pubblicate** per **HTTP** e **HTTPS**. Le porte predefinite sono rispettivamente la porta TCP 80 e la porta TCP 443. Modificare i valori di queste porte a seconda della configurazione dei servizi Web interni e dell'uso dei servizi di bilanciamento del carico (hardware e DNS).

    > [!IMPORTANT]
    > I servizi Web esterni e le porte di attesa e pubblicate definite sono riservate ai client e ai dispositivi esterni. I client e i dispositivi esterni usano le porte di attesa e pubblicate dei servizi Web esterni, in genere definite dal proxy inverso insieme al nome di dominio completo (FQDN) definito per tali servizi. La relazione dell'FQDN dei servizi Web esterni e gli URL semplici definiscono gli indirizzi URL (Uniform Resource Locator) che verranno usati dai client esterni per accedere ai servizi disponibili per gli utenti e i dispositivi esterni. Per informazioni dettagliate sugli URL semplici, vedere [Planning for Simple URLs](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx).

  **Mediation Server**

- Per configurare le proprietà di **Mediation Server** per un Mediation Server collocato (ovvero un Mediation Server distribuito nel front end server o nel pool Front End), selezionare **abilitato Mediation Server collocato**.

- Per definire le **porte di attesa** per un Mediation Server collocato, digitare il valore della porta **TLS** e **TCP** su cui è in attesa il Mediation Server collocato. Il valore predefinito di TLS è la porta TCP 5067.

- Per definire un valore per la porta TCP per il Mediation Server, selezionare la casella di controllo **Abilita porta TCP** . Per impostazione predefinita, il Mediation Server utilizza il protocollo TLS (Transport Layer Security) su TCP. Le porte TCP sono disponibili solo quando l'opzione Abilita la porta TCP è selezionata.

    > [!NOTE]
    > Questa è un'impostazione facoltativa e, per determinare se sia necessaria, è consigliabile consultare i requisiti del gateway o della rete PSTN in uso. Il valore predefinito della porta TCP è 5068.

- È necessario definire i trunk associati al Mediation Server collocato. Se sono già stati definiti, i trunk potranno essere associati al Mediation Server.

    Se si dispone di più di un gateway associato a un Mediation Server, è possibile specificare il gateway predefinito selezionando il gateway che si desidera impostare come predefinito e facendo clic su **Rendi predefinito**. Se si vuole rimuovere il gateway predefinito corrente, selezionarlo e fare clic su **Annulla predefinito**.

> [!IMPORTANT]
> Se si apportano modifiche alle proprietà in questa finestra di dialogo, è necessario pubblicare la topologia ed eseguire la distribuzione guidata di Skype for Business Server su tutti i server coinvolti. Dopo la pubblicazione della nuova topologia, è disponibile un elenco dei server in cui è in esecuzione la distribuzione guidata di Skype for Business Server come collegamento nella schermata di riepilogo della pubblicazione della topologia completata. Per informazioni dettagliate sulla pubblicazione della topologia aggiornata, vedere [Publish the Topology](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx). Per informazioni dettagliate sulla distribuzione guidata di Skype for Business Server, vedere [strumenti di amministrazione di Lync Server](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx).

Fare clic su **OK** per salvare le modifiche al documento della topologia.

Fare clic su **Annulla** per ignorare le modifiche e chiudere le **proprietà di modifica** per il front end server o il pool Front end.

Fare clic su **?** per leggere questo argomento della Guida.

## <a name="see-also"></a>Vedere anche

[Definire e configurare un pool Front End o un server Standard Edition](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)
