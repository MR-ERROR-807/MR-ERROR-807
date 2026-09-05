<p align="center">
  <img src="https://wakatime.com/badge/user/839267df-3912-44c6-97f4-9e3f0425b716.svg" alt="Total time coded since July 10 2009" />
</p><p align="center">
  <img height="25" src="https://api.visitorbadge.io/api/VisitorHit?user=MR-ERROR-807&countColor=%234a12ba" alt="Profile Views"/>
  <img height="25" src="https://img.shields.io/github/followers/MR-ERROR-807?color=4a12ba&style=for-the-badge&logo=github&label=Follow" alt="Followers"/>
  <img height="25" src="https://img.shields.io/github/stars/MR-ERROR-807?color=4a12ba&style=for-the-badge&logo=github&label=Stars" alt="Stars"/>
</p><p align="center"> 
    <img src="https://github-readme-streak-stats-eta-three.vercel.app?user=MR-ERROR-807&theme=tokyonight&hide_border=true" alt="GitHub Streak" width="60%">
</p>package kittyy

import "fmt"

type Profile interface {
	Contact() string
	Languages() []string
	Coding() CodingProfile
	Socials() SocialProfile
}

type CodingProfile struct {
	Editors      []string
	Specialities []string
	Languages    map[string][]string
}

type SocialProfile struct {
	Facebook  string
	Instagram string
	Telegram  string
}

type Ethan struct{}

func (Ethan) Contact() string {
	return ".kittyy"
}

func (Ethan) Languages() []string {
	return []string{"Philippines", "English", "Filipino"}
}

func (Ethan) Coding() CodingProfile {
	return CodingProfile{
		Editors:      []string{"GoLand", "PyCharm", "VS Code"},
		Specialities: []string{"Reverse Engineering", "Automation"},
		Languages: map[string][]string{
			"pro":          {"Go", "Python"},
			"intermediate": {"C++"},
			"learning":     {"WebAssembly"},
		},
	}
}

func (Ethan) Socials() SocialProfile {
	return SocialProfile{
		Facebook:  "https://facebook.com/kittyyypogi",
		Instagram: "https://instagram.com/kittyyyypogi",
		Telegram:  "https://t.me/kleinethanpogi",
	}
}

func main() {
	var me Profile = Ethan{}

	fmt.Println("contact:", me.Contact())
	fmt.Println("languages:", me.Languages())

	c := me.Coding()
	fmt.Println("editors:", c.Editors)
	fmt.Println("specialities:", c.Specialities)
	fmt.Println("coding languages:", c.Languages)

	s := me.Socials()
	fmt.Println("facebook:", s.Facebook)
	fmt.Println("instagram:", s.Instagram)
	fmt.Println("telegram:", s.Telegram)
}
