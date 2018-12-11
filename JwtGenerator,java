
//package com.thed.zapi.cloud.sample;

import java.io.IOException;
import java.io.UnsupportedEncodingException;
import java.net.URI;
import java.net.URISyntaxException;

import org.apache.http.HttpEntity;
import org.apache.http.HttpResponse;
import org.apache.http.ParseException;
import org.apache.http.client.ClientProtocolException;
import org.apache.http.client.HttpClient;
import org.apache.http.client.methods.HttpGet;
import org.apache.http.entity.StringEntity;
import org.apache.http.impl.client.DefaultHttpClient;
import org.apache.http.util.EntityUtils;

import com.thed.zephyr.cloud.rest.ZFJCloudRestClient;
import com.thed.zephyr.cloud.rest.client.JwtGenerator;

/**
 * @author swapna.vemula 12-Dec-2016
 *
 */
public class sampleJwtGenerator {

	/**
	 * @param args
	 * @author Created by swapna.vemula on 12-Dec-2016.
	 * @throws URISyntaxException
	 * @throws JobProgressException
	 * @throws JSONException
	 * @throws IOException 
	 * @throws IllegalStateException 
	 */
	public static void main(String[] args) throws URISyntaxException, IllegalStateException, IOException {
		// Replace Zephyr BaseUrl with the <ZAPI_CLOUD_URL> shared with ZAPI Cloud Installation
		String zephyrBaseUrl = "https://prod-api.zephyr4jiracloud.com/connect";
		// zephyr accessKey , we can get from Addons >> zapi section
		String accessKey = "MjQ0NjU0ZmEtNTUzNi0zZGRiLWE4ODktMjYyMDYyZjJhNTk4IGFkbWluIFVTRVJfREVGQVVMVF9OQU1F";
		// zephyr secretKey , we can get from Addons >> zapi section
		String secretKey = "bYuxqjx8YTbjb_Oped_GV-vP3lHdg97l2Bo3Z9ZJoNM";
		// Jira UserName
		String userName = "admin";
		ZFJCloudRestClient client = ZFJCloudRestClient.restBuilder(zephyrBaseUrl, accessKey, secretKey, userName).build();
		JwtGenerator jwtGenerator = client.getJwtGenerator();
		
		// API to which the JWT token has to be generated
		String createCycleUri = zephyrBaseUrl + args[0];
		
		URI uri = new URI(createCycleUri);
		int expirationInSec = 20000;
		String jwt = jwtGenerator.generateJWT("GET", uri, expirationInSec);
		
		// Print the URL and JWT token to be used for making the REST call
		System.out.println("FINAL API : " +uri.toString());
		System.out.println("JWT Token : " +jwt);	

	
	}

}
