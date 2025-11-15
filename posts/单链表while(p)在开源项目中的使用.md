#singly linked list


<br>static void buffer_check_tail(struct folio *folio, size_t size)<br>{<br>    struct buffer_head *head = folio_buffers(folio);<br>    struct buffer_head *tail;<br>    struct buffer_head *bh = head;<br>    do {<br>        tail = bh;<br>        bh = bh->b_this_page;<br>    } while (bh);  // while (bh != NULL)<br>    tail->b_this_page = head;<br>}<br>
