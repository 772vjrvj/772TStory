filter / asList / contains / count



List<String> names = Arrays.asList("jeong", "pro", "jdk", "java");

// 기존의 코딩 방식

long count = 0;

for (String name : names) {

  if (name.contains("o")) {

​    count++;

  }

}

System.out.println("Count : " + count); // 2



// 스트림 이용한 방식

count = 0;

count = names.stream().filter(x -> x.contains("o")).count();

System.out.println("Count : " + count); // 2



출처: https://jeong-pro.tistory.com/165 [기본기를 쌓는 정아마추어 코딩블로그]