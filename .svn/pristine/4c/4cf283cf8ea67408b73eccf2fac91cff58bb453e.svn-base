package org.cloudfoundry.samples.music;

import static org.junit.Assert.assertEquals;
import static org.junit.Assert.assertNotNull;

import java.util.List;

import org.cloudfoundry.samples.music.domain.Album;
import org.junit.Test;
import org.junit.runner.RunWith;
import org.springframework.boot.test.SpringApplicationConfiguration;
import org.springframework.http.HttpEntity;
import org.springframework.http.HttpMethod;
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.test.context.ActiveProfiles;
import org.springframework.test.context.junit4.SpringJUnit4ClassRunner;
import org.springframework.web.client.RestTemplate;


@RunWith(SpringJUnit4ClassRunner.class)
@SpringApplicationConfiguration(classes=TestApplication.class)

public class SystemTestingApplicationTests {

RestTemplate restTemplate = new RestTemplate();
//@Value("${serviceUrl.SpringMusic}")
//private String musicServiceURL = "http://localhost:8090/";
private String musicServiceURL = "http://demo-springboot-ms-basophil-effervescency.app.13.91.94.205.cf.pcfazure.com/";
//"https://demo-springboot-ms-basophil-effervescency.app.13.91.94.205.cf.pcfazure.com/"; 
//"http://localhost:8080/";
@Test
public void saveAlbum() {
Album album = new Album("System Testing", "STS", "","Spring Boot Test");
HttpEntity<Album> requestHttpEntity = new HttpEntity<>(album);

ResponseEntity<Album> responseEntity = restTemplate.exchange(musicServiceURL+"albums",
HttpMethod.PUT, requestHttpEntity, Album.class);
//
//List<Album> responseAlbum = restTemplate.getForObject(musicServiceURL+"albums", List.class);
assertNotNull(responseEntity);
assertEquals(HttpStatus.OK,responseEntity.getStatusCode());
System.out.println(responseEntity);
Album responseAlbum = responseEntity.getBody();
assertNotNull(responseAlbum); assertNotNull(responseAlbum.getId());
//Album responseAlbum = responseEntity.getBody();
//assertNotNull(responseAlbum.getId());
}

}

