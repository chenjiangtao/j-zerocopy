# j-zerocopy

  while(true) {
			  SocketChannel conn = listener.accept();
			  System.out.println("Accepted : "+conn);
			  conn.configureBlocking(true);
			  int nread = 0;
			  while (nread != -1)  {
				  try {
					  nread = conn.read(dst);
				  } catch (IOException e) {
					  e.printStackTrace();
					  nread = -1;
				  }
				  dst.rewind();
			  }
		  }
