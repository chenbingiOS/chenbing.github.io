初级 iOS 开发工程师面试题

2.写一个NSString类的实现

(id)initWithCString:(const char *)nullTerminatedCString encoding:(NSStringEncoding)encoding;

(id)stringWithCString: (const char*)nullTerminatedCString encoding: (NSStringEncoding)encoding { NSString *obj; obj = [self allocWithZone: NSDefaultMallocZone()]; obj = [obj initWithCString: nullTerminatedCString encoding: encoding]; return AUTORELEASE(obj); }

Objective-C 有多重继承吗？不是的画