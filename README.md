Zendesk-API
===========

Basic Zendesk API PHP implementation

use as follow 

	$zendesk = new zendesk($apiKey, $user, $subDomain, $suffix = '.json', $test = false);
	$arr 	 = array("z_subject"=>"Help, my printer is on fire!",
		   "z_description"=>"help I need some help",
		   "z_recipient"=>"RECIPIENTEMAIL@EMAIL.EMAIL",
		   "z_name"=>"REQUESTERNAME",
		   "z_requester"=>"REQUESTEREMAIL@EMAIL.EMAIL"
		  );
	$create  = json_encode(array('ticket' => array('subject' => $arr['z_subject'], 'description' => $arr['z_description'], 'requester' => array('name' => $arr['z_name'], 'email' => $arr['z_requester']))), JSON_FORCE_OBJECT);
	$data    = $zendesk->call("/tickets", $create, "POST");
	var_dump($data);

	print $data->ticket->id;

You're done !

Credits to Adam [https://support.zendesk.com/entries/21462093-php-and-zendesk-quick-start-guide](https://support.zendesk.com/entries/21462093-php-and-zendesk-quick-start-guide)
and Darren Scerri [https://github.com/darrenscerri](https://github.com/darrenscerri)
