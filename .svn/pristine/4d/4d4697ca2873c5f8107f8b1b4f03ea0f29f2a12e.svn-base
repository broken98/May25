package org.cloudfoundry.samples.music;

import static org.junit.Assert.*;

//import org.cloudfoundry.samples.music.SpringMusicApplication;
import org.cloudfoundry.samples.music.domain.Album;
import org.cloudfoundry.samples.music.web.AlbumController;
//import org.cloudfoundry.samples.music.repositories.inmemory.InMemoryAlbumRepository;
import org.junit.Test;
import org.junit.runner.RunWith;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.SpringApplicationConfiguration;
import org.springframework.test.context.ActiveProfiles;
//import org.springframework.boot.test.context.SpringBootTest;
//import org.springframework.test.context.ActiveProfiles;
//import org.springframework.test.context.junit4.SpringRunner;
import org.springframework.test.context.junit4.SpringJUnit4ClassRunner;

@RunWith(SpringJUnit4ClassRunner.class)
@SpringApplicationConfiguration(classes=Application.class)
@ActiveProfiles("in-memory")
public class UnitTest {

@Autowired
AlbumController controller;
@Test
public void testAddAlbums() {
Album inAlbum = new Album("Rolling in the Deep", "Adele", "2011", "pop");
Album savedAlbum = controller.add(inAlbum);
System.out.println("test " +savedAlbum.getTitle());
assertNotNull(savedAlbum.getId());
}

///update
@Test
public void testUpdateAlbums() {
Album inAlbum = new Album("Rolling", "Adele", "2011", "rock");
Album savedAlbum = controller.update(inAlbum);
System.out.println("test " +savedAlbum.getTitle());
assertEquals(savedAlbum.getTitle(),"Rolling");
}

/*@Test
public void testFindAlbum(){
Album inAlbum = new Album("Hello", "Adele", "2015", "pop");
Album savedAlbum = repository.save(inAlbum);
assertNotNull(savedAlbum.getId());
String albumId = savedAlbum.getId();
Album foundAlbum = repository.findOne(albumId);
assertNotNull(foundAlbum.getId());
assertEquals(inAlbum.getTitle(),foundAlbum.getTitle());
assertEquals(inAlbum.getArtist(),foundAlbum.getArtist());
assertEquals(inAlbum.getReleaseYear(),foundAlbum.getReleaseYear());
assertEquals(inAlbum.getGenre(),foundAlbum.getGenre());
System.out.println("Found Album " + foundAlbum);
}
@Test
public void testDeleteAlbum(){
Album inAlbum = new Album("Believer", "Imagine Dragons", "2017", "Alternative/Indie");
Album savedDeleteAlbum = repository.save(inAlbum);
assertNotNull(savedDeleteAlbum.getId());
System.out.println("Found Album " + savedDeleteAlbum);
repository.delete(savedDeleteAlbum);
Album findDeletedAlbum = repository.findOne(savedDeleteAlbum.getId());
assertNull(findDeletedAlbum);
}
@Test
public void testContainAlbum(){
Album inAlbum = new Album("Counting Stars", "OneRepublic", "2017", "Teen Pop");
inAlbum.setId(new RandomIdGenerator().generateId());
assertFalse(repository.exists(inAlbum.getId()));
System.out.println("Found Album " + inAlbum);

Album savedAlbum = repository.save(inAlbum);
assertNotNull(savedAlbum.getId());
assertEquals(inAlbum.getId(),savedAlbum.getId());
assertTrue(repository.exists(inAlbum.getId()));
}*/

}

